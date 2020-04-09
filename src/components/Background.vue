<template>
    <div class="background">
        <img :src="require(`@/assets/background/${src}`)" alt="Background">
        <img :src="require(`@/assets/background/${src}`)" alt="Background" class="blur1" v-if="blur >= 1">
        <img :src="require(`@/assets/background/${src}`)" alt="Background" class="blur2" v-if="blur >= 2">
        <img :src="require(`@/assets/background/${src}`)" alt="Background" class="blur3" v-if="blur >= 3">
        <img :src="require(`@/assets/background/${src}`)" alt="Background" class="blur4" v-if="blur >= 4">
    </div>
</template>

<script>
    export default {
        name: "Background",
        props: {
            src: String,
            blur: Number
        }
    }
</script>

<style scoped lang="scss">
.background {
    z-index: -99;
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;

    img {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .blur1 {
        filter: blur(1vh);
    }

    .blur2 {
        filter: blur(3vh);
    }

    .blur3 {
        filter: blur(5vh);
    }

    .blur4 {
        filter: blur(7vh);
    }
}
</style>