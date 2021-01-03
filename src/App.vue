<template>
  <div id="app">
    <AppHeader />
    <Lista />
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Lista from './components/Lista.vue'
import AppHeader from "@/components/AppHeader";

export default {
  name: 'App',
  components: {
    AppHeader,
    Lista,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  /*color: #2c3e50;*/
  /*margin-top: 60px;*/
}
</style>
