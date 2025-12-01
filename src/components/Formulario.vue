<script setup>
defineProps({
    valor1: {
        type: Number,
        required: true,
    },
    valor2: {
        type: Number,
        required: true,
    },
    operacao: {
        type: String,
        required: true,
    },
    })
    defineEmits(['update:valor1', 'update:valor2', 'update:operacao'])
</script>

<template>
    <form @submit.prevent class="text-center m-5 p-5 bg-light rounded-3">
        <h1 class="mb-5">Calculadora</h1>

        <input :value="valor1" @input="$emit('update:valor1', +$event.target.value)" type="number" class="rounded-3 ms-3" placeholder="Digite o número">
        <input :value="valor2" @input="$emit('update:valor2', +$event.target.value)" type="number" class="rounded-3 ms-3" placeholder="Digite o número">

        <select :value="operacao" @change="$emit('update:operacao', $event.target.value)" class="mb-5 ms-3" title="escolha a operação">
        <option value="adicao">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
        </select>
    </form>
</template>