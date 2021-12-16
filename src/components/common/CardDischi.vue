<template>
    <div id="card">
        <img :src="disco.poster" alt="">
        <h4 class="title">{{disco.title}}</h4>
        <p class="author">{{disco.author}}</p>
        <p class="year">{{disco.year}}</p>
    </div>
</template>

<script>
export default {
    name: "CardDischi",
    props: {
        disco: Object
    }
}
</script>

<style lang="scss" scoped>
@import "../../assets/style/variables.scss";
    #card {
        margin: 5px;
        img {
            width: 100%;
        }
        .title {
            color: white;
            margin: 15px 0;
            text-transform: uppercase;
        }
        .author, .year {
            color: $tertiary-color;
        }
    }
</style>