<!-- Script -->
<script setup>
    let nomes = ['Alice', 'Bruna', 'Caio', 'Daniel', 'Elise', 'Fabio', 'Gabriel', 'Higor']
</script>

<!-- HTML -->
 <template>
    <ul>
        <li v-for="nome in nomes">{{ nome }}</li>
    </ul>
 </template>