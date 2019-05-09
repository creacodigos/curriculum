<template>
  <footer>
    <div>
      {{ nombre }} - @creacodigos 
    </div>
  </footer>    
</template>

<script>
export default {
	name: 'CrFooter',
    data() {
        return {
            nombre: this.$parent.datos.datos.nombre
        }
    }
}
</script>