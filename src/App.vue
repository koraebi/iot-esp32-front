<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <EspSelector/>
</template>

<script>
import EspSelector from './components/EspSelector.vue'

export default {
  name: 'App',
  components: {
    EspSelector
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
