<template>
    <div class='container'>
        <p class='text'>hoi</p>
    </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class GameBox extends Vue {
    
}
</script>
<style scoped>
    .container {
        border: 6px rgb(213, 213, 213) solid;
        border-radius: 40px;
        height: 400px;
        width: 600px;
        display: flex;
        justify-content: center;
    }
</style>