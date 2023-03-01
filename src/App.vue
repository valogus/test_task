<script setup>
import Tabs from './components/Tabs.vue'
import Tab from './components/Tab.vue'
</script>

<template>
    <Tabs>
        <Tab title="Vue">Content of Vue Tab</Tab>
        <Tab title="HTML">Content of HTML Tab</Tab>
        <Tab title="SCSS">Content of SCSS Tab</Tab>
    </Tabs>
</template>

<style>
* {
    box-sizing: border-box;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
