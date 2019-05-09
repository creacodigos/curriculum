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
//import elements from "./assets/frameworks.json";

export default {
	name: 'App',
	components: {
		'cr-header': Header,
		'cr-nav': Nav,
		'cr-main': Main,
		'cr-footer': Footer
	}
};
</script>

<style>
  @import url("https://fonts.googleapis.com/css?family=Barlow+Condensed:300,400");
  @import url("https://fonts.googleapis.com/css?family=Marvel:400,700");
  @import url("https://fonts.googleapis.com/css?family=Saira+Condensed:100,300,500,700");
  @import url("./assets/css/reset.css");
  @import url("./assets/css/style.css");
  @import url("https://use.fontawesome.com/releases/v5.8.1/css/all.css");
</style>
