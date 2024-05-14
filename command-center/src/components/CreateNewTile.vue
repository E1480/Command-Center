<script setup>
const props = defineProps({
    func: Event,
    name: String,
    link: String

})
</script>

<template>
<form @submit.prevent="func">
        <h1>Create a New Tile</h1>
        <input v-bind="name" placeholder="Title" required><br/>
        <input v-bind="link" placeholder="Link e.g. Google.com"><br/>
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