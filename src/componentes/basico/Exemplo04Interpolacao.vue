<!-- Script -->
<script setup>
    let texto = '<p style="color:red">Hello World</p>'
</script>

<!-- HTML -->
<template>
    <div v-html="texto"></div>
    <div>{{ texto }}</div>
</template>