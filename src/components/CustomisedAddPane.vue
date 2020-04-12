<template>
    <el-form :model="websiteForm" :rules="rules" label-position="top" ref="websiteForm" class="demo-ruleForm">
        <el-form-item label="Website location" prop="url">
            <el-input v-model="websiteForm.url" placeholder="https://"></el-input>
        </el-form-item>
        <el-form-item label="Website name" prop="name">
            <el-input v-model="websiteForm.name" placeholder="Website name"></el-input>
        </el-form-item>
        <el-form-item label="Website icon" prop="icon">
            <el-upload
                    class="avatar-uploader"
                    action="https://jsonplaceholder.typicode.com/posts/"
                    :show-file-list="false"
                    :on-success="handleIconSuccess"
                    :before-upload="beforeIconUpload">
                <img v-if="websiteForm.icon" :src="websiteForm.icon" class="avatar" alt="Website icon">
                <i v-else class="el-icon-plus avatar-uploader-icon"></i>
            </el-upload>
        </el-form-item>
        <el-form-item label="Website color" prop="color">
            <el-color-picker v-model="websiteForm.color" show-alpha></el-color-picker>
        </el-form-item>
        <el-form-item>
            <el-button type="primary" @click="submitForm()">Add</el-button>
            <el-button @click="resetForm()">Reset</el-button>
        </el-form-item>
    </el-form>
</template>

<script>
    export default {
        name: "CustomisedAddPane",
        data() {
            return {
                websiteForm: {
                    url: "",
                    name: "",
                    icon: "",
                    color: null
                },
                rules: {
                    url: [
                        {required: true, message: "Website location is required", trigger: "blur"}
                    ],
                    name: [
                        {required: true, message: "Website name is required", trigger: "blur"}
                    ],
                    icon: [
                        {required: true, message: "Website icon is required", trigger: "blur"}
                    ],
                    color: [
                        {required: true, message: "Website color is required", trigger: "blur"}
                    ]
                }
            };
        },
        methods: {
            submitForm() {
                this.$refs["websiteForm"].validate((valid) => {
                    if (valid) {
                        console.log(this.websiteForm);
                        this.$root.$emit("addWebsite", this.websiteForm)
                    } else {
                        return false;
                    }
                });
            },
            resetForm() {
                this.$refs["websiteForm"].resetFields();
            },
            handleIconSuccess(res, file) {
                this.websiteForm.icon = URL.createObjectURL(file.raw);
            },
            beforeIconUpload(file) {
                const isImage = file.type === "image/jpeg" || file.type === "image/png";
                const isLt2M = file.size / 1024 / 1024 < 2;

                if (!isImage) {
                    this.$message.error("Icon can only be JPG or PNG format!");
                }
                if (!isLt2M) {
                    this.$message.error("Icon should be less than 2MB!");
                }
                return isImage && isLt2M;
            }
        }
    }
</script>

<style scoped lang="scss">
    .avatar-uploader {
        .el-upload {
            border: 1px dashed #d9d9d9;
            border-radius: 6px;
            cursor: pointer;
            position: relative;
            overflow: hidden;

            &:hover {
                border-color: #409EFF;
            }
        }

        .avatar-uploader-icon {
            font-size: 28px;
            color: #8c939d;
            width: 178px;
            height: 178px;
            line-height: 178px;
            text-align: center;
        }

        .avatar {
            width: 178px;
            height: 178px;
            display: block;
        }
    }
</style>