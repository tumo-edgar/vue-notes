<template>
    <Card :abc="number" />
    <button @click="increment">Click me</button>
</template>

<script setup>
  import {ref} from 'vue';
  import Card from './components/Card.vue'

  let number = ref(0)

  const increment = () => {
    number.value++
  }
</script>

<style scoped>
  h1 {
    color: red;
    font-weight: 900;
    font-size: 50px;
    margin: 100px;
  }
  button {
    margin-left: 100px;
  }
</style>