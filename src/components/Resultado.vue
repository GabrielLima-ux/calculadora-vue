<script setup>
const props = defineProps(['exibeResultado'])
</script>

<template>
    <div class="row">
        <div class="col text-center">
            <h2>Resultado: {{ Number(props.exibeResultado.toFixed(2)) }}</h2>
        </div>
    </div>
</template>