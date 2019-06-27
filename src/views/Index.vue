<template>
    <div class="index">
        初始化页面
        <div>
            <el-button type="primary" class="submit_btn" @click="hello()">Hello</el-button>
        </div>
        <br>
        <div>
            <el-button type="primary" class="submit_btn" @click="roleAdmin()">ROLE_ADMIN</el-button>
        </div>
    </div>
</template>

<script>

    export default {
        name: "index",
        components: {},
        methods: {
            hello() {
                console.log(localStorage.getItem("token"))
                this.$axiox
                    .get("/api/users/hello", {
                        headers: {
                            "Authorization": localStorage.getItem("token")
                        }
                    })
                    .then(res => {
                        console.log("返回值" + res.data)
                    });
                this.$router.push("/index")
            },
            roleAdmin() {
                console.log(localStorage.getItem("token"))
                this.$axiox
                    .get("/api/users/admin", {
                        headers: {
                            "Authorization": localStorage.getItem("token")
                        }
                    })
                    .then(res => {
                        console.log("返回值" + res.data)
                    });
                this.$router.push("/index")
            }
        }
    }
</script>

<style scoped>

</style>