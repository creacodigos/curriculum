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
      <div id="back-to-top" class="top" @click="scrollToTop()">
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
    },
    checkScroll: function(){
        return window.scrollY;
        },
    mostrarSubir: function(){

      window.onscroll = function() {

          let elemento = document.getElementById("back-to-top");
          elemento.classList.remove('show','fadein','delay2');

          if(window.scrollY > 200)
          elemento.classList.toggle('show','fadein','delay2');

      }
    }

  },
    mounted() {
        this.mostrarSubir();
    }
}
</script>

<style scoped>
footer{
  text-transform:none;
  font-size: 1rem;
}

#back-to-top{
  position: fixed;
  bottom: 2rem;
  right: 1rem;
	opacity: 0;
}
#back-to-top i{
  font-size: 3rem;
  color: #43cbff;
  cursor: pointer;
}
#back-to-top.show {
	opacity: 1;
}

.redes i{
  font-size: 2rem;
  margin: 1rem;
}
.redes a i{
  color: white;
}

@media (max-width: 767px ){

	#back-to-top {
		right: 0;
		bottom: 2rem;
	}

	#back-to-top.show {
		opacity: 0.75;
	}
}

</style>