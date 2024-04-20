<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const operacoes = reactive({
  operador: '',
  numeros: [
    {
      campoA: '',
      campoB: '',
    },
  ],
  resultado: '',
})

const calcular = () => {
  const { operador } = operacoes;
  switch (operador) {
    case 'adicao':
      return adicao();
    case 'subtracao':
      return subtracao();
    case 'multiplicacao':
      return multiplicacao();
    case 'divisao':
      return divisao();
  }
}

const adicao = () => {
  operacoes.resultado = parseInt(operacoes.numeros[0]) + parseInt(operacoes.numeros[1]);
}
const subtracao = () => {
  operacoes.resultado = parseInt(operacoes.numeros[0]) - parseInt(operacoes.numeros[1]);
}
const multiplicacao = () => {
  operacoes.resultado = parseInt(operacoes.numeros[0]) * parseInt(operacoes.numeros[1]);
}
const divisao = () => {
  operacoes.resultado = parseInt(operacoes.numeros[0]) / parseInt(operacoes.numeros[1]);
}
</script>

<template>
  <div class="container pt-5 mx-auto border boder-success rounded">
    <Cabecalho></Cabecalho>
    <Formulario :primeiro-numero="evento => operacoes.numeros[0] = evento.target.value"
      :segundo-numero="evento => operacoes.numeros[1] = evento.target.value"
      :recebe-operador-e-calcula="evento => operacoes.operador = evento.target.value" v-on="calcular()">
    </Formulario>
    <Resultado :existe-operador="operacoes.operador" :exibe-resultado="operacoes.resultado">

    </Resultado>
  </div>
</template>
