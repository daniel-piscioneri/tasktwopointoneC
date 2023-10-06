<template>
    <div>
        <h1>This forms part of task 2.1C</h1>
        <h1 v-if="awesome">Task is awesome</h1>
        <h1 v-else>Not Awesome</h1>
        
        
    </div>
    <h1 v-show="ok">hello</h1>

</template>

<script setup>
import { ref } from 'vue'

const awesome = ref(true);
const ok = ref(false);

</script>

<style>
div{
  color: black;
}

@media (min-width: 1024px) {
  .project {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

</style>