<template>
    <section>
        <div class="container">
            <SelectGenre @search="searchCharacters" :info="characters"/>
            <div v-for="(disco,index) in dischiFiltered" :key="index" class="card-dischi">
                <CardDischi :disco="disco"/>
            </div>
        </div>
    </section>
</template>

<script>
import CardDischi from "./CardDischi.vue";
import SelectGenre from "./SelectGenre.vue";
import axios from "axios";
export default {
    name: "SectionDischi",
    components: {
        CardDischi,
        SelectGenre
    },
    data() {
        return {
            characters: null,
            payload: ""
        }
    },
    created() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((response) => {
            this.characters = response.data.response;
            console.log(this.characters);
        })
        .catch(function (error) {
            console.log(error);
        });
    },
    methods: {
        searchCharacters(payload) {
            this.payload = payload;
            console.log(payload);
        }
    },
    computed: {
        dischiFiltered() {
            const arrayFiltered = this.characters.filter( (elm) => {
                console.log(elm);
                return elm.genre.includes(this.payload)
            });
            return arrayFiltered;
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../../assets/style/variables.scss";
    .container {
        display: flex;
        justify-content: space-around;
        align-items: center;
        flex-wrap: wrap;
    }   
    .card-dischi {
        width: calc(100% / 5 - 10px);
        min-height: 300px;
        margin: 30px 0;
        background-color: $primary-color;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
    }
</style>