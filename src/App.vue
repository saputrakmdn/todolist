<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> 
    <Header msg="Header"/>
    <LastRowFixed/> -->
    <todo/>
  </div>
</template>

<script>
import Vue from 'vue'
import VueMaterial from 'vue-material'
import 'vue-material/dist/vue-material.min.css'
import 'materialize-css/sass/materialize.scss';
// eslint-disable-next-line
import 'materialize-css/dist/js/materialize.min.js';

Vue.use(VueMaterial)

import todo from './components/todo.vue'
export default {
  name: 'app',
  components: {
   
    todo
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
