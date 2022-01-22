<template>
    <div class="cartItem">
        <img :src="image" alt="">
        <h4>{{name}}</h4>
        <p>{{price}}</p>
        <img src="../assets/remove.svg" alt="">
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
    img {
        height: 5rem;
        width: 5rem;
        object-fit: cover;
        margin-right: 2rem;
    }
    h4 {
        margin-right: 2rem;
    }
    
</style>