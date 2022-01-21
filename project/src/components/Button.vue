<template>
    <div class="button">
        <button>Add to Cart</button>
    </div>
</template>

<script>
    export default {}
</script>

<style>
    button {
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
    button:hover {
        cursor: pointer;
        opacity: 0.8;
    }
    button:active {
        transform: scale(0.96);
    }
</style>