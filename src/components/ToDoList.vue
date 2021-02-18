<template>
    <div class='container'>
        <ul class='list'>
            <li v-bind:key="i" v-for="i in toDoItems">
                <to-do :text="i"/>
            </li>
            <li>
                  <form @submit.prevent="createToDo()">
                      <input class='input' type='text' v-model="inputText" :text="inputText" placeholder="Enter text here..."/>
                 </form>
            </li>
        </ul>
         
        <!-- <form @submit.prevent="createToDo()">
            <input class="input--main" type='text' v-model="inputText"/>
            <button class="button--main" type='submit'/>
        </form> -->
    </div>
</template>

<script lang='ts'>
import { Options, Vue } from 'vue-class-component'
import ToDo from './ToDo.vue'

@Options ({
    components: {
        'to-do': ToDo
    }
})
export default class GameBox extends Vue {
    toDoItems: any[] = []
    inputText: string = ""

    createToDo() {
        this.toDoItems.push(this.inputText)
        this.inputText = ''
    }
}
</script>
<style scoped>
    .container {
        border: 6px #bad9b5 solid;
        border-radius: 12px;
        height: 70vh;
        width: 80vw;
        background: white;
        display: flex;
        flex-direction: column;
    }
/* 
    .input--main {
        border: 2px rgb(213, 213, 213) solid;
        border-radius: 3px;
    } */

    .input {
        border: none;
    }

    .button--main {
        height: 20px;
    }
</style>