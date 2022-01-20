<template>
    <div class="buttons">
        <button>test</button>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style>
.buttons {
    display: flex;
    justify-content: center;
    align-items: center;
}
button {
    background-color: #151515;
    color: #fff;
    border: none;
    border-radius: 0.2rem;
    height: 4rem;
    width: 10rem;
    font-size: 2rem;
    margin: 1rem;
    transition: all 0.3s;
}
button:hover {
    background-color: rgba(21, 21, 21, 0.7);
    cursor: pointer;
}
</style>