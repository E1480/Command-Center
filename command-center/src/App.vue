<script setup>
import { ref } from 'vue';
import NavComp from './components/Nav.vue';
import Tile from './components/Tile.vue'

const CenterTitle = ref('Command Center')
const TileName = ref('Title')

</script>

<template>
    <nav>
        <NavComp :title="CenterTitle" />
    </nav>
    <main>
        <Tile :title="TileName"/>
    </main>
</template>

<style scoped>

</style>
