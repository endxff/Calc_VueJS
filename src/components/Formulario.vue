<script setup>
const props = defineProps(['primeiroNumero', 'segundoNumero', 'recebeOperadorECalcula'])
</script>

<template>
    <form class="mx-auto w-50 pt-3 d-flex">
        <input @keyup="props.primeiroNumero" class="col-5 text-center border border-warning w-25" type="number"
            placeholder="10">
        <select @change="props.recebeOperadorECalcula" class="text-center form-control mx-3">
            <option disabled selected value>-- Operação --</option>
            <option value="adicao">Adição</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
        </select>
        <input @keyup="props.segundoNumero" class="col-5 text-center border border-warning w-25" type="number"
            placeholder="10">
    </form>
</template>