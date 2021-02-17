<template>
    <div class='container'>
        <ul v-bind:key="i" v-for="i in hoi">
            <to-do/>
        </ul>
    </div>
</template>

<script lang='ts'>
import { Component, Vue } from 'vue-property-decorator'
import ToDo from './ToDo'
@Component ({
    components: {
        ToDo
    }
})
export default class GameBox extends Vue {
    hoi: number[] = [1,2,3]
}
</script>
<style scoped>
    .container {
        border: 6px rgb(213, 213, 213) solid;
        border-radius: 12px;
        height: 70vh;
        width: 80vw;
        background: white;
    }
</style>