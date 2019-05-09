<template>
  <header>
    <div class="ok">
      <i class="fas fa-thumbs-up"></i>
    </div>
    <h1>{{ datos.nombre }}</h1>
    <h2 class="fino">
      {{ datos.cargo }}
    </h2>
  </header>
</template>

<script>
export default {
	name: 'CrHeader',
    data() {
        return {
            datos: this.$parent.datos.datos
        }
    }
}
</script>