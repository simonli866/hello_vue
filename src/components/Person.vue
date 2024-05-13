<template>
        <!-- html -->
        <div class="person">
                <h2>一辆{{ car.brand }}车，价值{{ car.price }}元</h2>
                <button @click="changeBrand">修改车商</button>
                <button @click="changePrice">修改车价</button>
                <button @click="changeCar">修改车</button>
                <br />
                <h2>
                        当前求和为：{{ sum }}
                </h2>
                <button @click="changeSum">修改sum</button>
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
import { reactive, ref } from "vue";
// 数据
let car = ref({
        brand: "benz",
        price: 100
})
let games = reactive([
        { id: "assss", name: "王者荣耀" },
        { id: "fasdfsd", name: "原神" },
        { id: "asdfasdf", name: "绝地求生" },
])

let sum = ref(0)

function changeBrand() {
        car.value.brand = "bmw";
}
function changePrice() {
        car.value.price += 20;
        sum = ref(9)
}
function changeCar() {
        // car = reactive({ brand: "bmw", price: 200 })
        // Object.assign(car, { brand: "bmw", price: 200 })
        car.value = { brand: "bmw", price: 200 }
}
function changeFirstGame() {
        games[0].name = "欧洲杯"
}
function changeSum() {
        sum.value += 1;
        sum = ref(6)
}
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
