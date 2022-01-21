<template>
    <div class="card">
        <img :src="image" alt="">
        <h2>{{title}}</h2>
        <p>{{about}}</p>
        <Button class="addCart"/>
    </div>
</template>

<script>
    import Button from "../components/Button.vue"

    export default {
        name: "card",
        components: {
            Button
        },
        props: {
            title: String,
            image: String,
            about: String,
        }
    }
</script>

<style>
    .card {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 20rem;
        height: 28rem;
        margin: 2rem;
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
        padding-top: 5rem;
        position: absolute;
        display: none;
    }
</style>