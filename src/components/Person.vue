<template>
        <!-- html -->
        <div class="person">
                <h2>需求：当水温达到60度，或水温达到80cm时，给服务器发请求</h2>
                <h2>当前水温：{{ temp }}</h2>
                <h2>当前水位：{{ height }}</h2>
                <button @click="changeTemp">水温+1</button>
                <button @click="changeHeight">水位+10</button>
        </div>
</template>

<!-- <script lang="ts">
// JS 或TS
export default {-
        // 组件名
        name: "Person",
};
</script> -->
<script lang="ts" setup name="Person">
import { ref, watch, watchEffect } from 'vue';
// 数据
let temp = ref(0);
let height = ref(10);

function changeTemp() {
        temp.value += 10;
}

function changeHeight() {
        height.value += 10;
}

// watch 实现
// watch([temp, height], (value) => {
//         // 从 value 中获取最新的水温，最新的水位
//         let [newTemp, newHeight] = value
//         if (newTemp >= 60 || newHeight >= 80) {
//                 console.log("给服务器发请求")
//         }
// })

// watchEffect实现
watchEffect(() => {
        if (temp.value >= 60 || height.value >= 80) {
                console.log("给服务器发请求")
        }
})

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
