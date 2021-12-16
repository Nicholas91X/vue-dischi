<template>
    <section>
        <CardDischi/>
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
        axios.get("https://api.sampleapis.com/rickandmorty/characters")
        .then(function (response) {
            console.log(response);
        })
        .catch(function (error) {
            console.log(error);
        });
    }
}
</script>

<style lang="scss" scoped>

</style>