<template>
    <div class="preview bg-light p-4 rounded">
        <h1 class="mb-4">{{ emoji }}</h1>
        <h2 class="mb-3"><strong>{{ titulo }}</strong></h2>
        <h3 class="mb-3"><strong>Y me parece {{ apreciacion }}</strong></h3>
        <h4 class="mb-3"><strong>He aprendido: <br> ["{{ competencias.length > 0 ? competencias.join('", "') : 'No seleccionado' }}"]</strong></h4>
        <p><strong>Mi opinión hasta ahora es:</strong> <br> {{ opinion }}</p>
    </div>
</template>

<script>
export default {
    name: 'VistaPrevia',
    props: {
        titulo: String,
        emoji: String,
        apreciacion: String,
        competencias: Array,
        opinion: String,
    },
};
</script>

<style scoped>
.preview {
    text-align: center;
    background-color: #f9f9f9;
    color: #2e3f50;
}
</style>