<template>
  <div id="app">
    <TextoComputado />
  </div>
</template>

<script>
import TextoComputado from './components/TextoComputado.vue'

export default {
  name: 'App',
  components: {
    TextoComputado
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-left: 60px;
}
</style>
