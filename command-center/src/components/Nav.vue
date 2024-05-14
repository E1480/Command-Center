<script setup>
import { ref } from 'vue';
    const title = ref("Title")
</script>

<template>
    <h1>{{ title }}</h1>
</template>

<style scoped>
body{
    color: white;
}
</style>