<template>
        <!-- html -->
        <div class="person">
                <!-- 情况五：监视多个数据 -->
                <h2>姓名：{{ person.name }}</h2>
                <h2>年龄：{{ person.age }}</h2>
                <h2>汽车：{{ person.car.c1 }}、{{ person.car.c2 }}</h2>
                <button @click="changeName">修改姓名</button>
                <button @click="changeAge">修改年龄</button>
                <button @click="changeC1">修改第一台汽车</button>
                <button @click="changeC2">修改第二台汽车</button>
                <button @click="changeCar">修改整个汽车</button>
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
import { reactive, watch } from 'vue';

let person = reactive({
        name: '张三',
        age: 18,
        sex: '男',
        car: {
                c1: "奔驰",
                c2: "宝马"
        }

});

function changeAge() {
        person.age += 1;
}
function changeName() {
        person.name += "~";
}

function changeC1() {
        person.car.c1 = "奔驰E级";
}

function changeC2() {
        person.car.c2 = "奔驰E级";
}

function changeCar() {
        person.car = {
                c1: "奔驰E级",
                c2: "宝马X5"
        }

}
// 监视。情况五：监视多个数据

watch([() => person.name, () => person.car.c1], (newValue, oldValue) => {
        console.log(newValue, oldValue)
}, { deep: true })
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
