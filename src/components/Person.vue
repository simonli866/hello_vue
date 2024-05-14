<template>
        <!-- html -->
        <div class="person">
                姓：<input type="text" v-model="firstName">
                名：<input type="text" v-model="lastName">
                全名：<span>{{ fullName }}</span>
                全名：<span>{{ fullName }}</span>
                全名：<span>{{ fullName }}</span>
                <button @click="changeFullName">改变全名</button>
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
import { computed, ref } from "vue";
let firstName = ref("张")
let lastName = ref("小")
// fullName 是被定义为了一个计算属性，且是只读的
// let fullName = computed(() => {
//         console.log("计算属性被调用")
//         return firstName.value.slice(0, 1).toUpperCase() + lastName.value.slice(1) + lastName.value
// })
// fullName 是被定义为了一个计算属性，且是可写的
let fullName = computed({
        get() {
                console.log("计算属性被调用")
                return firstName.value.slice(0, 1).toUpperCase() + lastName.value.slice(1) + lastName.value
        },
        set(newValue) {
                const [str1, str2] = newValue.split("-")
                firstName.value = str1
                lastName.value = str2
                console.log(newValue)
        }
})

function changeFullName() {
        fullName.value = "li-si"
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
