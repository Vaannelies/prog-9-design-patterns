<template>
    <div  @mouseover="visible = true" @mouseleave="visible = false">
        <input class='checkbox' type="checkbox" v-model="checked" />
        <input class='input' :class="checked ? 'input--checked' : false" type='text' :value='text'/>
        <button class='delete' v-if="visible" @click="deleteToDo">x</button>
    </div>
</template>

<script lang='ts'>
import { Vue  } from 'vue-class-component'
import { Prop } from 'vue-property-decorator';
import { IComponent } from './IComponent';

export default class ToDo extends Vue implements IComponent {
    @Prop({required: true}) text!: string;

    getHtml(): string {
   let  html = `
            <div  @mouseover="visible = true" @mouseleave="visible = false">
            <input class='checkbox' type="checkbox" v-model="checked" />   `

               html+= `
           <input class='input' :class="checked ? 'input--checked' : false" type='text' value='${this.text}'/>
                  `
        
      html+= `</div> `
        return html
      return this.text
    }


    visible: boolean = false
    checked: boolean = false

    deleteToDo() {
        this.$emit('delete')
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