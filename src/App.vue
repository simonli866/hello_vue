<template>
        <!-- html -->
        <div class="app">
                <h1>你好啊</h1>
                <Person />

        </div>
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

<style>
        /* css */
        .app{
                padding: 10px;
                background-color: #f5f5f5;
                box-shadow: 0 0 10px rgba(0,0,0,0.1);

        }
</style>