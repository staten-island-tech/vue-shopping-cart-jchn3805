<template>
    <div class="card">
        <img :src="image" alt="">
        <h2>{{name}}</h2>
        <p>{{price}}</p>
        <button @click="$emit('add')" class="addCart">Add to Cart</button>
    </div>
</template>

<script>
    export default {
        components: {
        },
        props: {
            name: String,
            image: String,
            price: String,
        }
    }
</script>

<style scoped>
    .card {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 20rem;
        height: 28rem;
        margin: 1.5rem;
        color: #151515;
        
    }
    .card:hover .addCart {
        display:block
    }
    
    img {
        width: 20rem;
        height: 20rem;
        object-fit: cover;
    }
    .addCart {
        margin-top: 5rem;
        position: absolute;
        display: none;
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
    .addCart:hover {
        cursor: pointer;
        opacity: 0.8;
    }
    .addCart:active {
        transform: scale(0.96);
    }
</style>