<script setup>
import { ref } from 'vue';

const props = defineProps({
    title: String,
    text_align: String
})


</script>

<template>

<div class="container" :class="text_align || 'center'">
    <h2>{{ title }}</h2>
</div>


</template>

<style scoped>

    .container{
        display: inline-block;
        padding: 1em;
        margin: 3em;
        /* Dimensions */
        width: 15em;
        height: 5em;
        /* Border */
        border: rgba(128, 128, 128, 0.123) 1px solid;
        border-radius: 10px;
        color: white;
        transition: 0.5s;
    }
    .container:hover{
        box-shadow: -5px 5px rgba(51, 51, 51, 0.603);
        transition: 0.5s;
    }

    .center{
        text-align: center;
    }
    .left{
        text-align: left;
    }
    .right{
        text-align: right;
    }
</style>