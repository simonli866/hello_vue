<template>
        <!-- html -->
        <div class="person">
                <h2>情况1:监视基本类型</h2>
                <h2>当前求和为：{{ sum }}</h2>
                <button @click="changeSum">sum+1</button>
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

let sum = ref(0);
function changeSum() {
        sum.value++;
}

const stopWatch = watch(sum, (newValue, oldValue) => {
        console.log("sum变化了", newValue, oldValue);
        if (newValue > 10) {
                stopWatch();
        }
})

console.log(stopWatch)
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
