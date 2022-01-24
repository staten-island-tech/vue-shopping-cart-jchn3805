<template>
  <div id="app">
    <div id="nav">
      <h1>Shop</h1>
      <h3 class="openCart">{{cartButton}}</h3>
      <div class="cart">
        <div class="itemList">
          <Item
          @remove="removeItem()"
          v-for="(inCart, index) in inCart"
          :key="index"
          :name="inCart.name"
          :price="`$${inCart.price}`"
          :image="inCart.image"
          />
        </div>
        <p>{{subtotal}}</p>
      </div>
    </div>
    <section class="display">
      <Card 
      @add="addCart(index)"
      v-for="(item, index) in items"
      :key="index" 
      :name="item.name" 
      :price="`$${item.price}`" 
      :image="item.image"
      />
    </section>
  </div>
</template>

<script>

import Card from "./components/Card.vue"
import Item from "./components/Item.vue"

export default {
  components: {
    Card, Item
  },
  data(){
    return {
      cartButton: `Cart`,
      inCart: [],
      items: [
        {
          name: "Lorem",
          price: 100,
          image: "https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80",
        },
        {
          name: "Ipsum",
          price: 100,
          image: "https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80",
        },
        {
          name: "Dolor",
          price: 100,
          image: "https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80",
        },
        {
          name: "Sit",
          price: 100,
          image: "https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80",
        },
        {
          name: "Amet",
          price: 100,
          image: "https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80",
        },
      ],
    }
  },
  methods: {
    addCart(index) {
      this.inCart.push(this.items[index])
    },
    removeItem() {
        this.inCart.pop()
    }
  }
}
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #151515;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  #nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 4rem;
    position: sticky;
    background-color: white;
    top: 0;
    z-index: 2;
  }

  #nav a {
    font-weight: bold;
    color: #151515;
    text-decoration: none;
  }

  #nav a.router-link-exact-active {
    color: #999999;
    text-decoration: none;
  }

  .display {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
  }

  .openCart {
    z-index: 1;
  }

  .openCart:hover {
    cursor: pointer;
    text-decoration: underline;
  }

  .openCart:hover ~ .cart {
    display: block;
  }

  .cart:hover {
    display: block;
  }

  .cart {
    display: none;
    position: fixed;
    top: 0;
    right: 0;
    padding-top: 4rem;
    min-height: 20rem;
    width: 22rem;
    background-color: #fff;
    z-index: 0;
    transition: 0.3s;
  }

</style>
