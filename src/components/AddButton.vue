<template>
    <button class="add-btn">
        <i class="fa-solid fa-plus"></i>
    </button>
</template>

<script setup>

</script>

<style scoped>
    .add-btn {
        position: fixed;
        right: 20px;
        bottom: 20px;
        width: 68px;
        height: 68px;
        border-radius: 50%;
        background: #4CCB90;
        border: 3px solid #FFFFFF;
        color: #ffffff;
        font-size: 30px;
        cursor: pointer;
        transition: 300ms;
    }

    .add-btn:hover {
        background: #30825c;
        transform: scale(1.2);
    }
</style>