<template>
  <div class="cart">
    <Item
    name="Lorem ipsum"
    price="$$$"
    image="https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80"
    />
  </div>
</template>

<script>
  import Item from "../components/Item.vue"

  export default {
    components: {
      Item
    }
  }
</script>

<style>
  .cart {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    margin-top: 2rem;
  }
</style>