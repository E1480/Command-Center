<script setup>
import { ref } from 'vue';
import NavComp from './components/Nav.vue';
import Tile from './components/Tile.vue';
import CreateNewTile from './components/CreateNewTile.vue';

let id = 0


const AppTitle = ref('Command Center')
const TileName = ref('')
const Link = ref('')

const Saved_Tiles = ref([
])

function addNewTile(){
    Saved_Tiles.value.push({id: id++, name:TileName.value, link:Link.value, align:'center'})
    TileName.value = ''
    Link.value = ''
}

</script>

<template>

    <CreateNewTile :func="addNewTile" :name="TileName" :link="Link" />

    <nav>
        <NavComp :title="AppTitle" class="nav">
            <button>Create New</button>
        </NavComp>
    </nav>

    <main>
        <Tile v-for="tiles in Saved_Tiles"
        :key="tiles.id"
        :title="tiles.name"
        :link="tiles.link"
        :text_align="tiles.align"/>
    </main>
</template>

<style scoped>

.nav button{
    transform:translate3D(0px,-0.5em,0px);
    margin-left: 3em;
}



</style>
