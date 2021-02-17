<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <p class="title">To do</p>
    <to-do-list/>
    <!-- <HelloWorld/> -->
  </div>
</template>

<script lang='ts'>
import { Component } from 'vue-property-decorator'
import Vue from 'Vue'
import ToDoList from './components/ToDoList';

@Component({
   components: {
     ToDoList,
   }
})
export default class App extends Vue {

}
</script>

<style lang='ts'>
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
    background-color: white;

    /* #177E89 */
    /* #084C61 */
    /* #DB3A34 */
    /* #FFC857 */
    /* #323031 */


    /* #eff7cf */
    /* #bad9b5 */
    /* #aba361 */
    /* #732c2c */
    /* #420c14 */
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
