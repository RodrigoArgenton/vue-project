<script setup>
  let nome = 'Alice'
  let idade = 38
  let numero1 = 5
  let numero2 = 10
</script>

<template>
  <p>{{ 'Olá ' + nome + ' sua idade é ' + idade}}</p>
  <p>{{ numero1 + numero2 }}</p>
</template>