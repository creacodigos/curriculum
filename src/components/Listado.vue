<template>
    <li v-if="dato.valor"><strong>{{ dato.name }}:</strong> <meter min="0" max="100" :value="dato.valor"></meter></li>
    
    <li v-else>
        <h5>{{ dato.titulo}}</h5>
        <h5 v-if="dato.name" class="cargo">
        {{ dato.name}}
        </h5>
        <p v-if="dato.info">
        {{ dato.info}}
        </p>
        <h6 v-if="dato.fechas" class="cargo">        
        {{ dato.fechas}}
        </h6>
    </li>    
</template>

<script>
export default {
    name: 'Listado',
    props: {
        dato: {
            type: Object,
            default: () => ({})
        },
        numid: {
            type: Number,
            default: 0
        }
    }
}
</script>
