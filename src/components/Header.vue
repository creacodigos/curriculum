<template>
  <header>
    <div class="dev">
      👨🏽‍💻
    </div>
    <div class="ok">
      <i class="fas fa-thumbs-up"></i>
    </div>
    <h1>{{ datos.datos.nombre }} </h1>
    <h2 class="fino">
      {{ datos.datos.cargo }}
    </h2>
  </header>
</template>

<script>
export default {
  name: 'CrHeader',
  data() {
    return this.$parent
  }
}
</script>