<template>
    <el-tabs v-model="activeName" type="border-card">
        <el-tab-pane>
            <span slot="label"><i class="el-icon-circle-plus"></i> Add</span>
            <AddPane/>
        </el-tab-pane>
        <el-tab-pane>
            <span slot="label"><i class="el-icon-user-solid"></i> My</span>
            用户管理
        </el-tab-pane>
        <el-tab-pane>
            <span slot="label"><i class="el-icon-s-tools"></i> Settings</span>
            配置管理
        </el-tab-pane>
    </el-tabs>
</template>

<script>
    import AddPane from "./AddPane";
    export default {
        name: "Sidebar",
        components: {AddPane},
        data() {
            return {
                activeName: "first"
            };
        }
    };
</script>

<style scoped lang="scss">
</style>