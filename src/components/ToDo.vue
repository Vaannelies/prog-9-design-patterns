<template>
   <input class='input' type='text' :value='text'/>
</template>

<script lang='ts'>
import { Vue, Options } from 'vue-class-component'
import { Component, Prop } from 'vue-property-decorator';

// @Options

// @Component
export default class ToDo extends Vue {
    // constructor(
    //     text: string,
    // )
    $refs!: {
        message: string,
    }
    @Prop({required: true}) text!: string;

    created() {
        console.log(this.text)
    }
    
    // text: string = ''

    // setName(t: string) {
    //     this.text = t
    //     // console.log(this.text)
    // }
    // text: string = 'hallo'
}
</script>

<style scoped>
    .input {
        border: none;
    }
</style>