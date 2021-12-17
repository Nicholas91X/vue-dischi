<template>
    <div>
        <select name="" id="select-genre" v-model="select">
            <option v-for="(disco,index) in info" :key="index" :value="disco.genre">{{disco.genre}}</option>
        </select>
        <button @click.prevent="$emit('search',select)">Search</button>
    </div>
</template>

<script>
export default {
    name: "SelectGenre",
    props: {
        info: Array
    },
    data() {
        return {
            select: ""
        }
    }
}
</script>

<style lang="scss" scoped>

</style>