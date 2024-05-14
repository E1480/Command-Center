<script setup>
import { ref } from 'vue';
import NavComp from './components/Nav.vue';


const title = ref("Command Center")

</script>

<template>
    <nav>
        <NavComp :title="title" />
    </nav>
    <main>
        
    </main>
</template>

<style scoped>

</style>
