<template>
    <el-tabs v-model="activeName">
        <el-tab-pane>
            <span slot="label">Default</span>
            用户管理
        </el-tab-pane>
        <el-tab-pane>
            <span slot="label">Customised</span>
            <CustomisedAddPane/>
        </el-tab-pane>
    </el-tabs>
</template>

<script>
    import CustomisedAddPane from "./CustomisedAddPane";
    export default {
        name: "AddPane",
        components: {CustomisedAddPane},
        data() {
            return {
                activeName: "first"
            };
        }
    }
</script>

<style scoped lang="scss">

</style>