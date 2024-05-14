<template>
        <!-- html -->
        <div class="person">
                <h2>姓名：{{ name }}</h2>
                <h2>age: {{ age }}</h2>
                <button @click="changeAge">change age</button>
                <button @click="changeName">change name</button>
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
import { reactive, toRef, toRefs } from 'vue';
let person = reactive({
        name: '张三',
        age: 18,
        sex: '男',
        hobby: ['打篮球', '踢足球', '打羽毛球'],
        address: {
                province: '北京',
                city: '北京',
                street: '东城'
        },
        say: function () {
                console.log('我是' + this.name + ',今年' + this.age + '岁,性别' + this.sex)

        }
})

let { name, age } = toRefs(person)
let x = toRefs(person)

let nl = toRef(person, 'name')
console.log(nl.value)

console.log(x)
function changeAge() {
        age.value += 1
        console.log(age)
}
function changeName() {
        name.value += '~'
        console.log(name)
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
