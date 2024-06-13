<!-- Script -->
<script setup>
    let validacao = false
</script>
<!-- css -->
<style>
    .true{
        color: green
    }
    .false{
        color: red
    }
</style>
<!-- HTML -->
<template>
    <h1 :class="validacao ? 'true' : 'false'">Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit blanditiis error et optio itaque. Quidem animi facere error exercitationem deserunt aliquam vitae consequatur, adipisci amet doloremque alias esse, dolorem tempore?</h1>
</template>