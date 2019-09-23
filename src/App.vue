<template>
  <div id="app">
    <img alt="Ron Swanson" src="./assets/images.jpeg">
    <Quote />
  </div>
</template>

<script>
import Quote from './components/Quote.vue'

export default {
  name: 'app',
  components: {
    Quote
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
