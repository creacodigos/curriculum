<template>
  <footer>
    <div>
      {{ datos.datos.nombre }} - @creacodigos 
    </div>
  </footer>    
</template>

<script>
export default {
	name: 'CrFooter',
  data() {
      return this.$parent
  }
}
</script>