<template>
    <div class="cartItem">
        <img :src="image" alt="">
        <h4>{{name}}</h4>
        <p>{{price}}</p>
        <img @click="$emit('remove')" src="../assets/remove.svg" alt="" class="remove">
    </div>
</template>

<script>
    export default {
        props: {
            name: String,
            image: String,
            price: String,
        }
    }
</script>

<style scoped>
    .cartItem {
        display: flex;
        align-items: center;
        justify-content: space-between;
        height: 5rem;
        margin: 2rem;
        color: #151515;
    }
    .cartItem:hover .remove {
        display: block;
    }
    img {
        height: 5rem;
        width: 5rem;
        object-fit: cover;
        margin-right: 2rem;
    }
    h4 {
        margin-right: 2rem;
    }
    .remove {
        position: absolute;
        margin-left: 1.5rem;
        width: 2rem;
        height: 2rem;
        opacity: 0.3;
        display: none;
        transition: 0.3s;
    }
    .remove:hover {
        cursor: pointer;
        opacity: 0.5;
    }
    .remove:active {
        transform: scale(0.9);
    }
    
</style>