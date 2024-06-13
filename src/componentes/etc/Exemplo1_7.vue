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

// Função para alternar a visibilidade
function visualizacaoBloco(opcao) {
    if(opcao == 'concatenacao'){
        blocoBooleanConcatencao.value = !blocoBooleanConcatencao.value
    }else if(opcao == 'condicional'){
        blocoBooleanCondicional.value = !blocoBooleanCondicional.value
    }else if(opcao == 'lacoRepeticao'){
        blocoBooleanLacoRepeticao.value = !blocoBooleanLacoRepeticao.value
    }else if(opcao == 'interpolacao'){
        blocoBooleanInterpolacao.value = !blocoBooleanInterpolacao.value
    }
}
// função que calcula a média
function calculoMedia(nota1, nota2, nota3){
    return (nota1 + nota2 + nota3)/3
}
// função que adiciona um nome a uma lista
function adicionarNome(){
    listaNomespessoas.value.push(nomePessoa.value)
    nomePessoa.value = ''
}
// função para trocar a cor do texto utilizando o v-html/interpolaçao
function trocarCor(cor){
    if(cor == 'padrao'){
        texto.value = ''
    }else if (cor == 'verde'){
        texto.value = '<p style="color:green">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus sapiente eos expedita cum quidem illo rem reprehenderit, ratione fugiat, harum delectus enim, quia commodi incidunt ad animi! Magnam, dignissimos velit?</p>'
    }else if (cor == 'amarelo'){
        texto.value = '<p style="color:yellow">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus sapiente eos expedita cum quidem illo rem reprehenderit, ratione fugiat, harum delectus enim, quia commodi incidunt ad animi! Magnam, dignissimos velit?</p>'
    }else if (cor == 'vermelho'){
        texto.value = '<p style="color:red">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus sapiente eos expedita cum quidem illo rem reprehenderit, ratione fugiat, harum delectus enim, quia commodi incidunt ad animi! Magnam, dignissimos velit?</p>'
    }else if (cor == 'preto'){
        texto.value = '<p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus sapiente eos expedita cum quidem illo rem reprehenderit, ratione fugiat, harum delectus enim, quia commodi incidunt ad animi! Magnam, dignissimos velit?</p>'
    }
}
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
            <button @click="visualizacaoBloco('concatenacao')">Concatenação</button>
            <div :class="blocoBooleanConcatencao ? 'mostrar' : 'esconder'">
                <h2>Concatenação de nome e sobrenome</h2>
                <input type="text" v-model="nome" placeholder="Digite o seu nome">
                <input type="text" v-model="sobrenome" placeholder="Digite o seu sobrenome">
                <P> Olá {{ nome + ' ' + sobrenome }}</P>
            </div>
        </div>
        <div class="mainCondicional">
            <button @click="visualizacaoBloco('condicional')">Condicional</button>
            <div :class="blocoBooleanCondicional ? 'mostrar' : 'esconder'">
                <h2>Calculo de média</h2>
                <input type="number" v-model="nota1" placeholder="Digite a primeira nota">
                <input type="number" v-model="nota2" placeholder="Digite a segunda nota">
                <input type="number" v-model="nota3" placeholder="Digite a terceira nota">
                <p>A média das notas inseridas é: {{ calculoMedia(nota1, nota2, nota3) }}</p>
            </div>
        </div>
        <div class="mainLacoRepeticao">
            <button @click="visualizacaoBloco('lacoRepeticao')">Laço de repetição</button>
            <div :class="blocoBooleanLacoRepeticao ? 'mostrar' : 'esconder'">
                <h2>Laço de repetição</h2>
                <input type="text" v-model="nomePessoa" placeholder="Digite um nome">
                <button @click="adicionarNome">Adicionar nome</button>
                <ul>
                    <li v-for="nomePessoa in listaNomespessoas">{{ nomePessoa }}</li>
                </ul>
            </div>
        </div>
        <div class="mainInterpolacao">
            <button @click="visualizacaoBloco('interpolacao')">Interpolação</button>
            <div :class="blocoBooleanInterpolacao ? 'mostrar' : 'esconder'">
                <h2>Interpolação</h2>
                <button @click="trocarCor('padrao')">Retirar Texto</button>
                <button @click="trocarCor('verde')">Verde</button>
                <button @click="trocarCor('amarelo')">Amarelo</button>
                <button @click="trocarCor('vermelho')">Vermelho</button>
                <button @click="trocarCor('preto')">Preto</button>
                <div v-html="texto"></div>
            </div>
        </div>
    </div>
</template>
