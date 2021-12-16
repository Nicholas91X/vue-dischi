<template>
    <main>
        <SectionDischi/>
    </main>
</template>

<script>
import SectionDischi from "../common/SectionDischi.vue";
export default {
    name: "Main",
    components: {
        SectionDischi
    }
}
</script>

<style lang="scss" scoped>
@import "../../assets/style/variables.scss";
    main {
        background-color: $secondary-color;
    }
</style>