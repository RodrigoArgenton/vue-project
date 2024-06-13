<!-- Script -->
<script setup>

    function mensagem(){
        alert('Mensagem de alerta')
    }

</script>

<!-- HTML -->

<template>
    <button @click="mensagem">Clique aqui para mostrar o alerta</button>
</template>