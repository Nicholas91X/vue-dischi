<template>
    <section>
        <div class="container">
            <div v-for="(disco,index) in characters" :key="index" class="card-dischi">
                <CardDischi :disco="characters[index]"/>
            </div>
        </div>
    </section>
</template>

<script>
import CardDischi from "./CardDischi.vue";
import axios from "axios";
export default {
    name: "SectionDischi",
    components: {
        CardDischi
    },
    data() {
        return {
            characters: null
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