<template>
    <div id="app">
        <Background src="wallhaven-512644.png"/>
        <el-main>
            <WebsiteDrawer :websites="websites"/>
            <el-button @click="drawer = true" type="primary" style="margin-left: 16px;">
                Add Website
            </el-button>
        </el-main>
        <el-drawer :visible.sync="drawer" :with-header="false">
            <Sidebar/>
        </el-drawer>
    </div>
</template>

<script>
    import Sidebar from "./components/Sidebar";
    import WebsiteDrawer from "./components/WebsiteDrawer";
    import Background from "./components/Background";
    export default {
        name: 'App',
        components: {Background, WebsiteDrawer, Sidebar},
        data() {
            return {
                drawer: false,
                websites: []
            };
        },
        mounted() {
            this.$root.$on("addWebsite", (website) => {
                this.websites.push(website);
            });
        }
    }
</script>

<style lang="scss">
    * {
        font-family: "Helvetica Neue", Helvetica, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "微软雅黑", Arial, sans-serif;
    }

    body {
        margin: 0;
    }

    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
    }

    .el-container {
        width: 100vw;
        height: 100vh;
    }

    .taskbar {
        width: 100%;
        background: rgba(0, 0, 0, 0.8);
    }

    .el-main {
        width: 100%;
    }
</style>
