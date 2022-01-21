<template>
    <div class="cartItem">
        <img :src="image" alt="">
        <h3>{{name}}</h3>
        <p>{{price}}</p>
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

<style>
    .cartItem {
        display: flex;
        align-items: center;
        justify-content: space-between;
        height: 7rem;
        width: 75%;
        margin: 1rem;
        background-color: #efefef;
        color: #151515;
    }
    h3 {
        padding-right: 40rem;
    }
    img {
        height: 7rem;
        width: 7rem;
        object-fit: cover;
    }
</style>