<script setup>
  import { reactive } from 'vue';
  import Formulario from './components/Formulario.vue';

  const estado = reactive({
    primeiroNumero: 0,
    segundoNumero: 0,
    filtro: 'adicao',
  })

  const adicao = ({ primeiroNumero, segundoNumero } = estado) => {
  return primeiroNumero + segundoNumero;
}

const subtracao = ({ primeiroNumero, segundoNumero } = estado) => {
  return primeiroNumero - segundoNumero;
}

const multiplicacao = ({ primeiroNumero, segundoNumero } = estado) => {
  return primeiroNumero * segundoNumero;
}

const divisao = ({ primeiroNumero, segundoNumero } = estado) => {
  return primeiroNumero / segundoNumero;
}

const resultado = () => {
  const {filtro} = estado;

    switch (filtro) {
      case 'subtracao':
        return subtracao();
      case 'multiplicacao':
        return multiplicacao();
      case 'divisao':
        return divisao();
      default:
        return adicao();    
    }
  }

</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 text-center">
        <h1>Calculadora:</h1>
    </header>
    <Formulario
      :trocar-filtro="(event) => (estado.filtro = event.target.value)"
      :numero1="(event) => (estado.primeiroNumero = Number(event.target.value))"
      :numero2="(event) => (estado.segundoNumero = Number(event.target.value))"
    />
    <br>
    <br>
    <h1 class="text-center border border-dark rounded p-5">O resultado é: {{ resultado() }} </h1>
  </div>
  
</template>

<style scoped>
</style>
