<template>
    <div  @mouseover="visible = true" @mouseleave="visible = false">
        <input class='checkbox' type="checkbox" v-model="checked" />
        <input class='input' :class="checked ? 'input--checked' : false" type='text' :value='text'/>
        <button class='delete' v-if="visible" @click="deleteToDo">x</button>
    </div>
</template>

<script lang='ts'> 
import { Prop } from 'vue-property-decorator'
import { Vue, Options} from 'vue-class-component'
import { IComponent } from './IComponent';

// @Options({})
export default class Project extends Vue implements IComponent {
    @Prop({required: true, public: true}) text!: string
    @Prop({required: true}) todos!: IComponent[]
    
    public visible: boolean = false
    checked: boolean = false
    public hoii: string = "hoi"

    deleteToDo() {
        console.log('deleteee')
        this.$emit('delete')
    }

    getHtml(): string {
        //   this.text =
        // return c
        // let html: string = "<ul><li>"
        // html += this.text
        // html += "<ul>"
        // this.todos.forEach(todo => {
        //     html +="<li>"
        //     html += todo.getHtml()
        //     html +="</li>"
        // })
        // html += "</ul>"
        // html += "</li></ul>"
      let  html = `
            <div  @mouseover="visible = true" @mouseleave="visible = false">
            <input class='checkbox' type="checkbox" v-model="checked" />   `

               html+= `
           <input class='input' :class="checked ? 'input--checked' : false" type='text' value='${this.text}'/>
            <div class="children">  `
           
           this.todos.forEach(todo => {
               html+=
                    todo.getHtml()
           })
      html+= `</div></div> `
        return html
            //    <p>${todo}</p>
        // <p>${this.text}</p>
            // <button class='delete' v-if="visible" onclick="${this.deleteToDo}">x</button>
    }

}
</script>

<style scoped>

    @import url('https://fonts.googleapis.com/css2?family=Varela+Round&display=swap');

    .input {
        border: none;
        font-size: 20px;
        font-family: 'Varela Round';

    }
  
    .input--checked {
        text-decoration: line-through;
        color: gray;
    }

    .children {
        margin-left: 10px;
    }

    .delete {
        border: 1px solid #420c14;
        border-radius: 2px;
        color: #420c14;
        background: #ed5252 ;
        margin-left: 10px;
        width: auto;
        font-size: 20px;
    }
    
    .checkbox {
        padding-top: 12px;
        background-color: grey;
        height: 20px;
        font-size: 20px;
        width: 20px;
        margin-right: 10px;
        
    }
    .checkbox:after {
        background-color: grey;
        height: 20px;
        font-size: 20px;
        width: 20px;
        margin-right: 10px;
        
    }

</style>