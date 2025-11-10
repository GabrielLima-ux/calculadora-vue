<script setup>
import { reactive } from 'vue'
import { ref } from 'vue'

  const num1 = ref(0)
  const num2 = ref(0)
  const resultado = ref(0)
  const operacao = ref('')

  function somar() {
    resultado.value = Number(num1.value) + Number(num2.value)
  }

  function subtrair() {
    resultado.value = Number(num1.value) - Number(num2.value)
  }

  function multiplicar() {
    resultado.value = Number(num1.value) * Number(num2.value)
  }

  function dividir() {
    resultado.value = Number(num1.value) / Number(num2.value)
  }

  function contas() {
    switch (operacao.value) {
      case 'adicao':
        return somar()
      case 'subtracao':
        return subtrair()
      case 'multiplicacao':
        return multiplicar()
      case 'divisao':
        return dividir()  
    }
  }

</script>

<template>

  <div class="container">
    <form @submit.prevent class="text-center m-5 p-5 bg-light rounded-3">
      <h1 class="mb-5">Calculadora</h1>
      <input @keyup="evento => contas() = evento.target.value" type="number" v-model="num1" class="rounded-3 ms-3" placeholder="Digite o número">
      <input @keyup="evento => contas() = evento.target.value" type="number" v-model="num2" class="rounded-3 ms-3" placeholder="Digite o número">
      <select v-model="operacao" class="mb-5" title="escolha a operação">
        <option value="adicao">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
      </select>
    </form>
    <div class="row">
      <div class="col text-center">
        <h2>Resultado: {{ resultado }}</h2>
      </div>
    </div>
  </div>

</template>

<style scoped>

  

</style> 
