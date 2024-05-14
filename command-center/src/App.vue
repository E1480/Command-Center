<script setup>
import { ref } from 'vue';
import NavComp from './components/Nav.vue';

</script>

<template>
    <nav>
        <NavComp :title="title" />
    </nav>
    <main>

    </main>
</template>

<style scoped>
    .container{
        display: inline-block;
        place-items: center;
        padding: 1em;
        margin: 3em;
        width: 15em;
        height: 5em;
        border: rgb(128, 128, 128) 1px solid;
        border-radius: 10px;
        color: white;
        transition: 0.5s;
    }
    .container:hover{
        box-shadow: -5px 5px rgba(51, 51, 51, 0.603);
        transition: 0.5s;
    }
    .container button{
        width: 100%;
        color: red;
    }
</style>
