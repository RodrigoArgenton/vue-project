<!-- Script -->
<script setup>
import { ref } from 'vue'

// Criar uma variável reativa
// blocos
let blocoBooleanConcatencao = ref(false)
let blocoBooleanCondicional = ref(false)
let blocoBooleanLacoRepeticao = ref(false)
let blocoBooleanInterpolacao = ref(false)
// concatenção
let nome = ref('')
let sobrenome = ref('')
// media
let nota1 = ref('')
let nota2 = ref('')
let nota3 = ref('')
// laço de repetição
let nomePessoa = ref('')
let listaNomespessoas = ref([])
// interpolação
let texto = ref('')

</script>

<!-- Css -->
<style>
/* classes das opções */
.mainConcatenacao,
.mainCondicional,
.mainLacoRepeticao,
.mainInterpolacao{
    width: 100%;
    height: 100%;
    text-align: center;
    margin-bottom: 10px;
}
/* Condicionais de visualização de bloco*/
.mostrar {
    display: block;
    margin-top: 10px;
}
.esconder {
    display: none;
}
</style>

<!-- HTML -->
<template>
    <div>
        <div class="mainConcatenacao">
            <button @click="blocoBooleanConcatencao = !blocoBooleanConcatencao">Concatenação</button>
            <div v-if="blocoBooleanConcatencao">
                <h2>Concatenação de nome e sobrenome</h2>
                <input type="text" v-model="nome" placeholder="Digite o seu nome">
                <input type="text" v-model="sobrenome" placeholder="Digite o seu sobrenome">
                <P> Olá {{ nome + ' ' + sobrenome }}</P>
            </div>
        </div>
        <div class="mainCondicional">
            <button @click="blocoBooleanCondicional = !blocoBooleanCondicional">Condicional</button>
            <div v-if="blocoBooleanCondicional">
                <h2>Calculo de média</h2>
                <input type="number" v-model="nota1" placeholder="Digite a primeira nota">
                <input type="number" v-model="nota2" placeholder="Digite a segunda nota">
                <input type="number" v-model="nota3" placeholder="Digite a terceira nota">
                <p>A média das notas inseridas é: {{ (nota1 + nota2 + nota3)/3 }}</p>
            </div>
        </div>
        <div class="mainLacoRepeticao">
            <button @click="blocoBooleanLacoRepeticao = !blocoBooleanLacoRepeticao">Laço de repetição</button>
            <div v-if="blocoBooleanLacoRepeticao">
                <h2>Laço de repetição</h2>
                <input type="text" v-model="nomePessoa" placeholder="Digite um nome">
                <button @click="listaNomespessoas.push(nomePessoa)">Adicionar nome</button>
                <ul>
                    <li v-for="nomePessoa in listaNomespessoas">{{ nomePessoa }}</li>
                </ul>
            </div>
        </div>
        <div class="mainInterpolacao">
            <button @click="blocoBooleanInterpolacao = !blocoBooleanInterpolacao">Interpolação</button>
            <div v-if="blocoBooleanInterpolacao">
                <h2>Interpolação</h2>
                <button @click="texto = ''">Retirar Texto</button>
                <button @click="texto = '<p style=color:green>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus sapiente eos expedita cum quidem illo rem reprehenderit, ratione fugiat, harum delectus enim, quia commodi incidunt ad animi! Magnam, dignissimos velit?</p>'">Verde</button>
                <button @click="texto = '<p style=color:yellow>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus sapiente eos expedita cum quidem illo rem reprehenderit, ratione fugiat, harum delectus enim, quia commodi incidunt ad animi! Magnam, dignissimos velit?</p>'">Amarelo</button>
                <button @click="texto = '<p style=color:red>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus sapiente eos expedita cum quidem illo rem reprehenderit, ratione fugiat, harum delectus enim, quia commodi incidunt ad animi! Magnam, dignissimos velit?</p>'">Vermelho</button>
                <button @click="texto = '<p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus sapiente eos expedita cum quidem illo rem reprehenderit, ratione fugiat, harum delectus enim, quia commodi incidunt ad animi! Magnam, dignissimos velit?</p>'">Preto</button>
                <div v-html="texto"></div>
            </div>
        </div>
    </div>
</template>
