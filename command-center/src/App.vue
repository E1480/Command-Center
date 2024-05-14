<script setup>
import { ref } from 'vue';
import NavComp from './components/Nav.vue';
import Tile from './components/Tile.vue';
import CreateNewTile from './components/CreateNewTile.vue';

let id = 0


const AppTitle = ref('Command Center')
const TileName = ref('')
const Link = ref('')
const Description = ref('')

const popUp = ref('hide')

const Saved_Tiles = ref([
])

function popup(){
    if(popUp.value == 'hide'){
        popUp.value = 'show'
    }else if(popUp.value == 'show'){
        popUp.value = 'hide'
    }
}


function addNewTile(){
    Saved_Tiles.value.push({
        id: id++,
        name:TileName.value,
        link:Link.value,
        desc:Description.value,
        align:'center'
    })

    TileName.value = ''
    Link.value = ''
    Description.value = ''

    if(popUp.value == 'show'){
        popUp.value = 'hide'
    }
}

</script>

<template>

        <CreateNewTile
            @response="addNewTile"
            v-model:name="TileName"
            v-model:link="Link"
            v-model:desc="Description"
            :class="popUp"
        />

    <nav>
        <NavComp :title="AppTitle" class="nav">
            <button @click="popup">Create New</button>
        </NavComp>
    </nav>

    <main>
        <Tile v-for="tiles in Saved_Tiles"
            :key="tiles.id"
            :title="tiles.name"
            :link="tiles.link"
            :description="tiles.desc"
            :text_align="tiles.align"
        />


        
    </main>
</template>

<style scoped>

.nav button{
    transform:translate3D(0px,-0.5em,0px);
    margin-left: 3em;
}


.hide{
    opacity: 0%;
    z-index: -1;
    transition: 1s;
}

.show{
    opacity: 100%;
    z-index: 1;
    transition: 1s;
}

</style>
