<script setup>
import { ref } from 'vue';
import NavComp from './components/Nav.vue';
import Tile from './components/Tile.vue'

let id = 0

const CenterTitle = ref('Command Center')
const TileName = ref('Title')

const Saved_Tiles = ref([
    {id: id++, name:'1', align: 'center'},
    {id: id++, name:'2', align: 'left'},
    {id: id++, name:'1', align: 'right'},
    {id: id++, name:'1', align: 'center'},
    {id: id++, name:'1', align: 'left'},
    {id: id++, name:'1', align: 'right'},
])

</script>

<template>
    <nav>
        <NavComp :title="CenterTitle" />
    </nav>
    <main>
        <Tile v-for="tiles in Saved_Tiles"
        :key="tiles.id"
        :title="tiles.name"
        :text_align="tiles.align"/>
    </main>
</template>

<style scoped>

</style>
