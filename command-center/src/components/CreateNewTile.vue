<script setup>

const emit = defineEmits(['response'])

function submit(){
    emit("response")
}

const name = defineModel('name')
const link = defineModel('link')
const desc = defineModel('desc')
const align = defineModel('align')

</script>

<template>
<form @submit.prevent="submit">
        <h1>Create a New Tile</h1>
        <input v-model="name" placeholder="Title" required><br/>
        <textarea v-model="desc" placeholder="Description"></textarea><br/>
        <input v-model="link" placeholder="Link e.g. Google.com"><br/>

        <label for="align">Select Alignment:</label><br/>
        <select v-model="align">
            <option disabled value="">Alignment</option>
            <option>left</option>
            <option>center</option>
            <option>right</option>
        </select>
        <br/>
        <button>Add</button>
    </form>
</template>

<style scoped>
form{
    text-align: center;
    border: white 2px solid;
    border-radius: 10px;
    width: fit-content;
    min-height: max-content;
    height: auto;
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

form select{
    color: black;
}
</style>