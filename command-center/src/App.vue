<script setup>
import { ref } from 'vue';
import NavComp from './components/Nav.vue';


const title = ref("Title")

</script>

<template>
    <NavComp :title="title" />
</template>

<style scoped>

</style>
