<template>
  <div id="app">
    <cr-header></cr-header>
    <cr-nav></cr-nav>
    <cr-main></cr-main>
    <cr-footer></cr-footer>
  </div>
</template>

<script>
import Header from './components/Header';
import Nav from './components/Nav';
import Main from './components/Main';
import Footer from './components/Footer';
//import data from './assets/data/data.json';
//import data from 'http://creacodigos.com/data/data.json';
import axios from 'axios'

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
      data: data
    };
  },
  methods: {
    leerDatos(){
      axios.get('https://creacodigos.com/data/data.json')
        .then(response => {
          console.log(response.data);
          this.datos = response.data;
        })
        .catch(function(error) {
          console.log('ERROR: '+ error);
        });
      }
    },
    created: function() {
      // Fetch Data
      this.leerDatos();
    }
};
</script>

<style>
  @import url("https://fonts.googleapis.com/css?family=Saira+Condensed:100,300,500,700");
  @import url("./assets/css/reset.css");
  @import url("./assets/css/style.css");
</style>
