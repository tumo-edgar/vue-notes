<template>
    <div class="card">
      <h2>
        {{ props.title }}
      </h2>

      <p class="text">
        {{ props.content }}
      </p>

      <p class="date">
        {{ props.date }}
      </p>
    </div>
</template>

<script setup>
    import { defineProps,ref } from 'vue';
    let props = defineProps(['title', 'content', 'date'])

    let text = ref('')

</script>

<style scoped>
  .card {
    width: 320px;
    height: 208px;
    background: linear-gradient(114.43deg, rgba(255, 255, 255, 0.6) 4%, rgba(255, 255, 255, 0.1) 100%);
    padding: 20px;
    border-radius: 14px;
  }
  h2 {
    font-weight: 700;
  }
  .text {
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 4;
    overflow: hidden;
    height: 96px;
  }
  .date {
    text-align: right;
    color: #5e5e5e;
    margin-top: 10px;
  }
</style>