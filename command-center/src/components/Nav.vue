<script setup>

 const props = defineProps({
    title : String
 })

</script>

<template>
    <div>
        <img src="../assets/logo.svg" alt="logo" class="logo">
        <h1>
            {{ title || " " }}
        </h1>
        <slot></slot>
    </div>
</template>

<style scoped>
h1{
    color: white;
    display: inline-block;
    transform:translate3D(0px,-5px,0px);
    
}
div{
    padding: 1em;
    background-color: rgb(46, 46, 46);
}
.logo{
    height: 2.5em;
    padding-right: 1em;
    display: inline-block;
    transform:translate3D(0px,5px,0px);
}
</style>