<template>
        <Person />
        <!-- <Person/> -->
</template>

<script lang="ts">
import Person from './components/Person.vue'

// JS 或TS
export default {
        // 组件名
        name: "App",
        components: {
                // 注册组件
                Person 
        }
}
</script>

