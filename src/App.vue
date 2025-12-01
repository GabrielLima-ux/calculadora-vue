<script setup>
import { ref, watch } from 'vue'

import Formulario from './components/Formulario.vue'
import Resultado from './components/Resultado.vue'

const estado = ref({
  valor1: 0,
  valor2: 0,
  operacao: 'adicao',
})
const resultado = ref(0)

function calcular() {
  const { valor1, valor2, operacao } = estado.value
  switch (operacao) {
    case 'adicao':
      resultado.value = valor1 + valor2
      break
    case 'subtracao':
      resultado.value = valor1 - valor2
      break
    case 'multiplicacao':
      resultado.value = valor1 * valor2
      break
    case 'divisao':
      resultado.value = valor2 !== 0 ? valor1 / valor2 : 0
      break
    default:
      resultado.value = 0
  }
}

// Observa mudanças no estado e recalcula
watch(estado, calcular, { deep: true })
</script>

<template>
  <div class="container">
    <Formulario
      v-model:valor1="estado.valor1"
      v-model:valor2="estado.valor2"
      v-model:operacao="estado.operacao"
    />
    <Resultado :exibe-resultado="resultado" />
  </div>
</template>

<style scoped>
</style>
