<template>
    <a :href="website.url">
        <el-card shadow="never">
            <el-image fit="cover" src="https://cdn.iconscout.com/icon/free/png-256/google-470-675827.png"/>
            <span>{{website.name}}</span>
        </el-card>
    </a>
</template>

<script>
    export default {
        name: "Website",
        props: {
            website: Object
        }
    }
</script>

<style scoped lang="scss">
    a {
        display: flex;
        text-decoration: none;

        .el-card {
            border: none;
            background: none;
            backdrop-filter: brightness(150%) blur(10px);
            transition: 0.3s;

            span {
                color: white;
            }

            &:hover {
                backdrop-filter: brightness(200%) blur(20px);
            }
        }
    }
</style>