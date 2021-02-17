<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <p class="title">GameBox</p>
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
  @import url('https://fonts.googleapis.com/css2?family=Varela+Round&display=swap');

  body {
    margin: 0;
  }
  #app {
    /* font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale; */
    /* text-align: center; */
    /* color: #2c3e50; */
    display:flex;
    height: 100vh;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    /* margin-top: 60px; */
    background-color: #084C61;

    /* #177E89 */
    /* #084C61 */
    /* #DB3A34 */
    /* #FFC857 */
    /* #323031 */
  }

  .title {
    font-family: 'Varela Round';
    font-size: 40px;
    font-weight: 1;
    margin-top: 0;
    color: #DB3A34;
    -webkit-text-stroke: 2px #FFC857;
  }
</style>
