<template>
  <div id="app">
    <img src="./assets/logo.png">
    <game-box/>
    <!-- <HelloWorld/> -->
  </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator'
import GameBox from './components/GameBox';

@Component({
   components: {
     'game-box': GameBox,
   }
})
export default class App extends Vue {

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
  background-color: #101130;
}
</style>
