<template>
    <div class="button">
        <input type="submit" id="addCart" value="Add to Cart">
    </div>
</template>

<script>
    export default {
        name: 'Button',
    }
</script>

<style>
    input {
        width: 12rem;
        height: 3rem;
        border: none;
        border-radius: 0.3rem;
        background-color: #151515;
        color: #fff;
        font-size: 0.9em;
        opacity: 0.6;
        transition: 0.3s;
    }
    input:hover {
        cursor: pointer;
        opacity: 0.8;
    }
    input:active {
        transform: scale(0.96);
    }
</style>