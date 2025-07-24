<template>
  <div class="main">
    <h1 class="title">Note App</h1>

    <div class="notes">
      <Card title="asojdhasidhjb" content="asiudhasijdb askjd askjbd ask" date="21-07-2333" />
    </div>

    <AddButton @click="toggleOpen" />

    <NoteForm v-if="isOpen" @onClose="toggleOpen" />
  </div>
</template>

<script setup>
  import {ref} from 'vue';
  import AddButton from './components/AddButton.vue';
  import Card from './components/Card.vue';
  import NoteForm from './components/NoteForm.vue';

  let isOpen = ref(false);

  function toggleOpen(){
    isOpen.value = !isOpen.value
  }

</script>

<style scoped>
  .main {
    width: 100%;
    min-height: 100vh;
    background: linear-gradient(128deg, rgba(135, 246, 180, 0.84) 12.75%, rgba(50, 180, 187, 0.67) 83.4%);
    padding: 32px;
  }
  .title {
    text-align: center;
    font-size: 42px;
    font-weight: 900;
  }
</style>