<template>
        <!-- html -->
        <div class="person">
                <h2>情况2:监视对象类型</h2>
                <h2>姓名:{{ person.name }}</h2>
                <h2>年龄：{{ person.age }}</h2>
                <button @click="changeName">修改姓名</button>
                <button @click="changeAge">修改年龄</button>
                <button @click="changePerson">修改对象</button>
        </div>
</template>

<!-- <script lang="ts">
// JS 或TS
export default {
        // 组件名
        name: "Person",
};
</script> -->
<script lang="ts" setup name="Person">
import { watch, ref } from "vue";
let person = ref({
        name: "张三",
        age: 18,
        sex: "男",
        address: "北京",
});
function changeAge() {
        person.value.age += 1;
}
function changeName() {
        person.value.name += "~";
}


function changePerson() {
        person.value = {
                name: "李四",
                age: 20,
                sex: "女",
                address: "上海",
        };
}

// 监视，情况一：监视ref定义的对象类型数据，监视的是对象的地址值，若想监视对象内部的属性，需要使用deep:true
// watch(person, (newValue, oldValue) => {
//         console.log("newValue", newValue);
//         console.log("oldValue", oldValue);
// }, {deep:true})
// watch 的第三个参数是配置对象
// watch 的第二个参数是监视的回调
// watch 的第一个参数是监视的对象
watch(person, (newValue, oldValue) => {
        console.log("newValue", newValue);
        console.log("oldValue", oldValue);
}, { deep: true, immediate: true })
</script>

<style scoped>
/* css */
.app {
        padding: 10px;
        background-color: #f5f5f5;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        border-radius: 10px;
}

.person {
        background-color: skyblue;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        padding: 10px;
}

button {
        margin: 0 5px;
}

li {
        font-size: 20px
}
</style>
