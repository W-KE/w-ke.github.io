<template>
    <el-row :gutter="20" type="flex" justify="center" class="dock">
        <el-col>
            <div class="app"><i class="el-icon-eleme"></i></div>
        </el-col>
        <el-col>
            <div class="app">App</div>
        </el-col>
        <el-col>
            <div class="app">App</div>
        </el-col>
        <el-col>
            <div class="app">{{ time | moment("LTS") }}</div>
        </el-col>
    </el-row>
</template>

<script>
    export default {
        name: "Dock",
        data: function () {
            return {
                time: new Date()
            };
        },
        mounted: function () {
            setInterval(() => {
                this.time = new Date()
            }, 1000)
        }
    }
</script>

<style scoped lang="scss">
    .dock {
        height: 100%;
        padding: 5px;

        .app {
            cursor: default;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100%;
            color: white;
            font-size: xx-large;
            border-radius: 4px;
            background: rgba(255, 255, 255, 0.3);
            overflow: hidden;

            &:hover {
                background: rgba(255, 255, 255, 0.8);
            }
        }

        .el-divider {
            height: 100%;
        }
    }
</style>