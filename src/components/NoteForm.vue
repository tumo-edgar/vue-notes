<template>
    <div class="wrapper">
        <div class="form">

            <button class="close" @click="$emit('onClose')">
                <i class="fa-solid fa-xmark"></i>
            </button>

            <p class="title">
                Title
            </p>
            <input />
            <textarea></textarea>
            <button class="save">Save</button>
        </div>
    </div>
</template>

<script setup>

</script>

<style scoped>
    .wrapper {
        width: 100%;
        height: 100%;
        position: fixed;
        background-color: rgba(0, 0, 0, 0.4);
        top: 0;
        left: 0;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .form {
        width: 580px;
        height: 600px;
        background: linear-gradient(114.43deg, rgba(255, 255, 255, 0.6) 4%, rgba(255, 255, 255, 0.1) 100%);
        border-radius: 14px;
        border: 1px solid #fff;
        padding: 28px;
        position: relative;
    }
    .title {
        font-size: 24px;
        font-weight: 500;
    }

    input {
        width: 100%;
        height: 40px;
        margin-top: 10px;
        border: none;
        border-radius: 4px;
    }

    textarea {
        width: 100%;
        height: 280px;
        border: none;
        border-radius: 4px;
        margin-top: 30px;
        resize: none;
    }

    .save {
        width: 100%;
        height: 40px;
        border-radius: 4px;
        border: none;
        margin-top: 50px;
        background: linear-gradient(90deg, #B4FBF3 0%, #23926F 100%);
        color: #fff;
        font-size: 24px;
        cursor: pointer;
    }

    .close {
        background: none;
        border: none;
        color: #fff;
        font-size: 30px;
        cursor: pointer;
        top: 20px;
        right: 20px;
        position: absolute;
    }
</style>