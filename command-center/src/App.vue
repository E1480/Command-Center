<script setup>
import { ref } from 'vue';
import NavComp from './components/Nav.vue';
import Tile from './components/Tile.vue'

let id = 0
let currName = 0

const CenterTitle = ref('Command Center')
const TileName = ref('Title')

const Saved_Tiles = ref([
])

function addNewTile(){
    Saved_Tiles.value.push({id: id++, name:currName++, align:'center'})
}

</script>

<template>
    <nav>
        <NavComp :title="CenterTitle" class="nav">
            <button>Test</button>
        </NavComp>
        <button @click="addNewTile">Add New</button>
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
