<template>
        <!-- html -->
        <div class="person">
                <h1>中国</h1>
                <h2 ref="title">北京</h2>
                <h3>天安门</h3>
                <button @click="showLog">输出H2元素</button>
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
import { ref, defineExpose } from 'vue';
// 创建一个title 用于存储ref标记的内容
let title = ref()
let a = ref(0)
let b = ref(1)
let c = ref(2)

defineExpose({ a, b, c })
function showLog() {
        console.log(title.value)
}
</script>

<!-- scoped 局部样式 必须加 -->
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
