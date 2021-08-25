<template>
  <div id="app">
    <From />
  </div>
</template>

<script>
import From from './components/from'
export default {
  name: 'App',
  components: {
    From
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
