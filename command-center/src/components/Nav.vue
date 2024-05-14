<script setup>

 const props = defineProps({
    title : String
 })

</script>

<template>
    <div>
        <img src="../assets/logo.svg" alt="logo" class="logo">
        <h1>
            {{ title || "No title" }}
        </h1>
        
    </div>
</template>

<style scoped>
h1{
    color: white;
    display: inline-block;
    transform:translate3D(0px,-10px,0px);
}
div{
    padding: 1em;
    background-color: rgb(46, 46, 46);
}
.logo{
    height: 2em;
    padding-right: 1em;
    display: inline-block;
}
</style>