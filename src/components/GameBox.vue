<template>
    <div class='container'>
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
        border-radius: 12px;
        height: 70vh;
        width: 80vw;
        background: white;
    }
</style>