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
        beforeCreate() {
                console.log("Person组件创建前");
        },
        setup() {
                console.log("Person组件创建后");
                // 数据
                // vue3中弱化了this，此时name，age，tel都不是响应式的
                let name = "张三" 
                // 此时的那么不是响应式的
                let age = 18
                let tel = "13333333"
                // 方法
                function changeName() {
                        name = "李四"
                }
                function changeAge() {
                        age +=1
                }
                function showTel() {
                        alert(tel)
                }
                return {
                        name,
                        age,
                        tel,
                        changeName,
                        changeAge,
                        showTel
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