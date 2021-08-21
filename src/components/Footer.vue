<template>
  <footer>
    <div>
      Desde 🏝 Tenerife para el mundo 🚀
      <div class="redes">
        <a href="https://github.com/creacodigos" target="_blank">
          <i class="fab fa-github"></i>
        </a>
        <a :href=`https://www.linkedin.com/in/${datos.datos.linkedin}/` target="_blank">
          <i class="fab fa-linkedin"></i>
        </a>
        <a href="https://twitter.com/creacodigos" target="_blank">
          <i class="fab fa-twitter"></i>
        </a>
      </div> 
      <div class="top" @click="scrollToTop()">
        <i class="fas fa-arrow-alt-circle-up"></i>
      </div>
    </div>
  </footer>    
</template>

<script>
export default {
	name: 'CrFooter',
  data() {
      return this.$parent
  },
  methods:{
    scrollToTop(){
      window.scrollTo({ top: 0, behavior: 'smooth' })
    }
  }
}
</script>

<style scoped>
footer{
  text-transform:none;
  font-size: 1rem;
}

.top{
  position: fixed;
  bottom: 2rem;
  right: 1rem;
}
.top i{
  font-size: 3rem;
  color: #43cbff;
  cursor: pointer;
}
.redes i{
  font-size: 2rem;
  margin: 1rem;
}
.redes a i{
  color: white;
}
</style>