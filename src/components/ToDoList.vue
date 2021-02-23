<template>
    <div class='container'>
        <ul class='list'>
            <li v-bind:key="(i, key)" v-for="(i, key) in toDoItems">
                <to-do :text="i" @delete="deleteToDo(key)"/>
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

    deleteToDo(key: any) {
        console.log(key)
       this.toDoItems.splice(key, 1)
       console.log(this.toDoItems)
    }
}
</script>
<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Varela+Round&display=swap');

    .container {
        padding-top: 20px;
        border: 6px #bad9b5 solid;
        border-radius: 12px;
        height: 70vh;
        width: 80vw;
        background: white;
        display: flex;
        flex-direction: column;
        overflow: auto;
    }

    .input {
        margin-left: 34px;
        border: none;
        font-size: 20px;
        font-family: 'Varela Round'
    }

    .list {
        list-style-type: none;
    }
</style>