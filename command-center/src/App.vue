<script setup>
import { ref } from 'vue';
import NavComp from './components/Nav.vue';
import Tile from './components/Tile.vue'

let id = 0


const AppTitle = ref('Command Center')
const TileName = ref('')
const Link = ref('')

const Saved_Tiles = ref([
])

function addNewTile(){
    Saved_Tiles.value.push({id: id++, name:TileName.value, link:Link, align:'center'})
    TileName.value = ''
    Link.value = ''
}

</script>

<template>

    <form @submit.prevent="addNewTile">
        <h1>Create a New Tile</h1>
        <input v-model="TileName" placeholder="Title" required><br/>
        <input v-model="Link" placeholder="Link"><br/>
        <button>Add</button>
    </form>

    <nav>
        <NavComp :title="AppTitle" class="nav">
            <button>Create New</button>
        </NavComp>
    </nav>
    <main>
        <Tile v-for="tiles in Saved_Tiles"
        :key="tiles.id"
        :title="tiles.name"
        :text_align="tiles.align"/>
    </main>
</template>

<style scoped>

.nav button{
    transform:translate3D(0px,-0.5em,0px);
    margin-left: 3em;
}
h1,h2,h3,h4,h5,h6,p{
    color: white;
}

form{
    text-align: center;
    border: white 2px solid;
    border-radius: 10px;
    width: fit-content;
    min-height: max-content;
    height: 15em;
    padding: 2em;
    background-color: rgba(0, 0, 0, 0.521);
    display: block;
    position:fixed;
    top: 30%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 1;
}

form *{
    margin: 5px;
    padding: 5px;
}
</style>
