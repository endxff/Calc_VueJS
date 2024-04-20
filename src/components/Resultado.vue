<script setup>
const props = defineProps(['existeOperador', 'exibeResultado'])
</script>

<template>
    <section class="resultado d-flex justify-content-center mt-5">
        <p v-if="props.existeOperador" class="fs-3 text-success p-2 border border-success">{{ props.exibeResultado }}
        </p>
    </section>
</template>