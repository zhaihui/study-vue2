<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <Communication /> -->
    <Slots />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import Communication from './components/communication'
import Slots from './components/slots'
export default {
  name: 'App',
  components: {
    // HelloWorld,
    // Communication,
    Slots
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
