<template>
    <header>
        <div class="logo">
            <img src="https://upload.wikimedia.org/wikipedia/commons/7/74/Spotify_App_Logo.svg" alt="Spotify Logo">
        </div>
    </header>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style lang="scss" scoped>
@import "../../assets/style/variables.scss";
    header {
        height: 50px;
        background-color: $primary-color;
        .logo {
            height: 50px;
            padding: 5px;
            margin-left: 10px;
            img {
                height: 100%;
            }
        }
    }
</style>