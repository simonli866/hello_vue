<template>
        <!-- html -->
        <div class="person">
                <h2>姓名：{{name}}</h2>
                <h2>年龄：{{age}}</h2>
                <button @click="changeName">修改名字</button>
                <button @click="changeAge">修改年龄</button>
                <button @click="showTel">查看联系方式</button>
        </div>
</template>

<script lang="ts">
// JS 或TS
export default {
        // 组件名
        name: "Person",
        data() {
                return {
                        name: "zhangsan",
                        age: 18,
                        tel: "xxxxxxx"
                }
        },
        methods: {
                changeName() {
                        this.name = "lisi"
                },
                changeAge() {
                        this.age +=1
                },
                showTel() {
                        alert(this.tel)
                }
        }
}
</script>

<style scoped>
        /* css */
        .app{
                padding: 10px;
                background-color: #f5f5f5;
                box-shadow: 0 0 10px rgba(0,0,0,0.1);
                border-radius: 10px;

        }
        .person{
                background-color: skyblue;
                box-shadow: 0 0 10px rgba(0,0,0,0.1);
                padding: 10px;

        }
        button{
                margin: 0 5px;
        }
</style>