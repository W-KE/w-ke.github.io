<template>
    <div class="main">
        <el-row :gutter="20" type="flex" justify="center" v-for="index in getRowCount(4)" :key="index">
            <el-col :span="4" v-for="app in getApps(4)[index - 1]" :key="app.id">
                <el-card :body-style="{ padding: '0px' }">
                    <img src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png" class="image">
                    <div style="padding: 14px;">
                        <span>{{app.name}}</span>
                        <div class="bottom clearfix">
                            <time class="time">{{ new Date() }}</time>
                            <el-button type="text" class="button">操作按钮</el-button>
                        </div>
                    </div>
                </el-card>
            </el-col>
        </el-row>
    </div>
</template>

<script>
    export default {
        name: "Desktop",
        data: function () {
            return {
                apps: [
                    {name: "TEST"},
                    {name: "TEST"},
                    {name: "TEST"},
                    {name: "TEST"},
                    {name: "TEST"},
                    {name: "TEST"},
                    {name: "TEST"},
                    {name: "TEST"},
                    {name: "TEST"},
                    {name: "TEST"},
                ]
            };
        },
        methods: {
            getRowCount: function (item_per_row) {
                return Math.ceil(this.apps.length / item_per_row);
            },
            getApps: function (item_per_row) {
                return Array.from({length: this.getRowCount(item_per_row)}, (v, i) =>
                    this.apps.slice(i * item_per_row, i * item_per_row + item_per_row)
                );
            }
        }
    }
</script>

<style scoped lang="scss">

</style>