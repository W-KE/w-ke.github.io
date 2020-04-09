<template>
    <div>{{title}}</div>
</template>

<script>
    export default {
        name: "Logo",
        props: {
            title: String
        }
    }
</script>

<style scoped>
    @import url("https://fonts.googleapis.com/css?family=Permanent+Marker");

    div {
        font-family: "Permanent Marker", serif;
        color: white;
        font-size: 500%;
    }
</style>