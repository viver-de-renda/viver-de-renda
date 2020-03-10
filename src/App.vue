<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <ViverRenda />
  </div>
</template>

<script>
import ViverRenda from './components/ViverRenda.vue'

export default {
  name: 'App',
  components: {
    ViverRenda
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
