<template>
    <div class="search">
        <input @keydown.enter="$emit('onSearch', text)" v-model="text" type="search">
        <button @click="$emit('onSearch', text)">
            <i class="fa-solid fa-magnifying-glass"></i>
        </button>
    </div>
</template>

<script setup>
    import {ref} from 'vue';

    let text = ref('');

</script>

<style scoped>
    .search {
        width: 350px;
        height: 40px;
        display: flex;
        gap: 8px;
    }
    input {
        flex: 1;
        border-radius: 4px;
        background-color: #fff;
        border: 1px solid #fff;
    }
    button {
        width: 40px;
        height: 40px;
        border-radius: 4px;
        background-color: #4CCB90;
        border: 1px solid #fff;
        cursor: pointer;
    }
</style>