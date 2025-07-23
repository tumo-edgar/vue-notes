<template>
    <div class="card">
      <h2>My Title</h2>
      <p class="text">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the i...</p>
      <p class="date">05-07-2025 20:30</p>
    </div>
</template>

<script setup>
    import { defineProps,ref } from 'vue';
    let props = defineProps(['abc'])

    let text = ref('')

</script>

<style scoped>
  .card {
    width: 320px;
    height: 208px;
    background: linear-gradient(114.43deg, rgba(255, 255, 255, 0.6) 4%, rgba(255, 255, 255, 0.1) 100%);

  }
</style>