<template>
        <h2 ref="title2">你好</h2>
        <button @click="showLog">点我输出h2</button>
        <Person ref="ren" />
</template>

<script lang="ts" setup name="App">
import Person from './components/Person.vue'
import { ref } from 'vue'
let title = ref()
let ren = ref()
function showLog() {
        // console.log(title.value)
        console.log(ren.value)
}
</script>
