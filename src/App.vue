<template>
  <div id="app" v-cloak>
    <section v-if="errored">
      <p>We're sorry, we're not able to retrieve this information at the moment, please try back later</p>
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
//import data from './assets/data/data.json';
//import axios from 'axios'

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
      //api : 'https://creacodigos.com/data/data.json',
      api : 'https://raw.githubusercontent.com/creacodigos/curriculum/master/src/assets/data/data.json',
      loading: true,
      errored: false
    }
  },
  created () {
    setTimeout(() => this.leerDatos(), 500);
  },
  methods: {
    leerDatos() {
      /*
      axios.get(this.api)
        .then(response => {
          console.log(response.data);
          this.datos = response.data;
        })
      */
      fetch(this.api)
          .then(response => response.json())
          .then(data => {
            //console.log(data)
            this.datos = data
            this.loading = false
          })
          .catch(error => {
            console.error('ERROR: '+ error)
            this.loading = true
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
