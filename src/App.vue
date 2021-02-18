<template>
  <div id="app">
    <p class="title">To do?</p>
    <to-do-list/>
  </div>
</template>

<script lang="ts">
import { Options, Vue} from 'vue-class-component'
import ToDoList from './components/ToDoList.vue'

@Options ({
  components: {
    'to-do-list': ToDoList
  }
})
export default class App extends Vue {
   hoi: string = 'hoi'
}

</script>
<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Varela+Round&display=swap');

  body {
    margin: 0;
  }
  #app {
    display:flex;
    color: #2c3e50;
    justify-content: center;
    flex-direction: column;
    height: 100vh;
    align-items: center;
    background-color: #eff7cf;
  }

  .title {
    font-family: 'Varela Round';
    font-size: 40px;
    font-weight: 1;
    margin-top: 0;
    color: #2c3e50;
    // -webkit-text-stroke: 2px #FFC857;
  }
  
    // #2c3e50
    /* #eff7cf */
    /* #bad9b5 */
    /* #aba361 */
    /* #732c2c */
    /* #420c14 */
</style>
