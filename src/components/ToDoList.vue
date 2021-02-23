<template>
    <div class='container'>
        <ul class='list'>
            <li v-bind:key="(i, key)" v-for="(i, key) in toDoItems">
                <!-- <to-do :text="i" @delete="deleteToDo(key)"/> -->
                <div @delete="deleteToDo(key)" v-html="i"></div>
                <button @click="deleteToDo(key)">x</button>
                <button @click="turnIntoProject(key)">+</button>
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
import { IComponent } from './IComponent'
import ToDo from './ToDo.vue'
import Project from './Project.vue'

@Options ({
    components: {
        'to-do': ToDo
    }
})
export default class ToDoList extends Vue {
    toDoItems: any[] = []
    inputText: string = ""

    createToDo() {
        // this.toDoItems.push(this.inputText)
        let todo: IComponent = new ToDo({text: this.inputText})
        let html = todo.getHtml()
        this.toDoItems.push(html)
        this.inputText = ''
    }

    deleteToDo(key: any) {
        console.log(key)
       this.toDoItems.splice(key, 1)
       console.log(this.toDoItems)
    }

    turnIntoProject(key: any) {
        console.log(Object.values(this.toDoItems[key]))
        let todo =  new ToDo({text: 'Enter text here...'})
        let project = new Project({text: this.toDoItems[key], todos: [todo]})
        // this.toDoItems.push(project.getHtml())
        this.toDoItems.splice(key, 1, project.getHtml())
    }
}
</script>
<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Varela+Round&display=swap');

    .children {
        margin-left: 10px;
    }
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