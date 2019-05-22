<template>
  <div id="app" v-cloak>
    <section v-if="errored">
      <p>Ouchh...!! Algo ha fallado de forma inesperada.<br>
      Por favor, inténtalo más tarde</p>
    </section>
    <section class="content" v-else>
      <div v-if="loading" id="loading">
        <i class="fas fa-sync"></i>
      </div>

      <section class="content" v-else>        
        <cr-header></cr-header>
        <cr-nav></cr-nav>
        <cr-main></cr-main>
        <cr-footer></cr-footer>
      </section>

    </section>
  </div>
</template>

<script>
import Header from './components/Header';
import Nav from './components/Nav';
import Main from './components/Main';
import Footer from './components/Footer';

export default {
    name: 'App',
    components: {
    'cr-header': Header,
    'cr-nav': Nav,
    'cr-main': Main,
    'cr-footer': Footer
  },
  data() {
    return {
      datos: [],
      api : 'https://raw.githubusercontent.com/creacodigos/curriculum/master/src/assets/data/data.json',
      loading: true,
      errored: false
    }
  },
  created () {
    this.leerDatos()
  },
  methods: {
    leerDatos() {
      fetch(this.api)
        .then(response => response.json())
        .then(data => {
          //console.log(data)
          this.datos = data
          setTimeout(() => this.loading = false, 500);
        })
        .catch(error => {
          console.error('ERROR: '+ error)
          this.loading = true
          this.errored = true
        })
    }
  }

}
</script>

<style>
  @import url("https://fonts.googleapis.com/css?family=Saira+Condensed:100,300,500,700");
  @import url("./assets/css/reset.css");
  @import url("./assets/css/style.css");
</style>
