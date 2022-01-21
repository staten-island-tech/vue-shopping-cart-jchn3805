<template>
  <div id="home">
    <Card 
    v-for="item in items"
    :key="item" 
    :name="item.name" 
    :price="`$${item.price}`" 
    :image="item.image"
    />
  </div>
</template>

<script>
// @ is an alias to /src

import Card from "../components/Card.vue"

export default {
  name: 'Home',
  components: {
    Card
  },
  data(){
    return {
      subtotal: 0,
      cartItems: 0,
      cart: [],
      totalPrice: [],
      items: [
        {
          name: "Lorem ipsum",
          price: 100,
          image: "https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80",
        },
        {
          name: "Lorem ipsum",
          price: 100,
          image: "https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80",
        },
        {
          name: "Lorem ipsum",
          price: 100,
          image: "https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80",
        },
      ],
    }
  },
  methods: {
    addToCart() {
      this.cart.push(this.items.name)
      this.totalPrice.push(this.items.price)
      this.subtotal = this.subtotal + this.items.totalPrice
    },
    remove() {
      if (this.order.length !==0) {
        
      }
    }
  }
}
</script>

<style>
  #home {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
  }
</style>
