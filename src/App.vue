<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- <Field/> -->
    <HelloWorld/>
  </div>
</template>

<script>
import Field from './components/Field'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // Field,
    HelloWorld
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
