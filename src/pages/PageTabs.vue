<template>
  <h1>Tabs</h1>
  <Tabs>
    <Tab title="Vue" id="vue">Content of Vue Tab</Tab>
    <Tab title="HTML" id="html">Content of HTML Tab</Tab>
    <Tab title="SCSS" id="scss">Content of SCSS Tab</Tab>
  </Tabs>
</template>

<script setup>
import Tabs from '@/components/Tabs.vue';
import Tab from '@/components/Tab.vue';
</script>
