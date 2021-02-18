<template>
    <div class='container'>
        <ul class='list'>
            <li v-bind:key="i" v-for="i in toDoItems">
                <to-do/>
            </li>
            <li>
                  <form @submit.prevent="createToDo(inputText)">
                      <input class='input' type='text' v-model="inputText" placeholder="Enter text here..."/>
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

        const newToDo = new ToDo('')
        this.toDoItems.push(newToDo)
        this.inputText = ''
        // newToDo.setName(this.inputText)
        // newToDo.text = this.inputText
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