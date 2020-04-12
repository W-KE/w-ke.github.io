<template>
    <div class="drawer">
        <el-row :gutter="20" v-for="index in getRowCount(8)" :key="index">
            <el-col :span="3" v-for="website in getWebsites(8)[index - 1]" :key="website.id">
                <Website :website="website"/>
            </el-col>
        </el-row>
    </div>
</template>

<script>
    import Website from "./Website";
    export default {
        name: "WebsiteDrawer",
        components: {Website},
        data: function () {
            return {
                apps: [
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                    {
                        url: "http://localhost:8080/",
                        name: "Website Name",
                        icon: "blob:http://localhost:8080/0b8fb8b6-81b1-4c9e-b893-1d398b627756",
                        color: "rgba(0, 21, 255, 1)"
                    },
                ]
            };
        },
        props: {
            websites: Array
        },
        methods: {
            getRowCount: function (item_per_row) {
                return Math.ceil(this.apps.length / item_per_row);
            },
            getWebsites: function (item_per_row) {
                return Array.from({length: this.getRowCount(item_per_row)}, (v, i) =>
                    this.apps.slice(i * item_per_row, i * item_per_row + item_per_row)
                );
            }
        }
    }
</script>

<style scoped lang="scss">
    .drawer {
        max-width: 1024px;
        margin: auto;
    }

    .el-row {
        margin-bottom: 20px;
    }
</style>