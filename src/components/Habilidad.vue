<template>
    <li><strong>{{ habilidad.name}}:</strong> <meter min="0" max="100" :value="habilidad.valor"></meter></li>
</template>

<script>
export default {
    name: 'Habilidad',
    props: {
        habilidad: {
            type: Object,
            default: () => ({})
        },
        numid: {
        type: String,
        default: 0
        }
    }
}
</script>
