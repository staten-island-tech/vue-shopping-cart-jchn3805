<template>
  <div id="home">
    <!-- <Card 
    name="Lorem ipsum"
    price="$$$"
    image="https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80"
    /> -->
    <Card v-for="destination in destinations" :key="destination" :title="destinations.name"/>
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
  destinations: [
    {
      name: "Lorem ipsum",
      price: 100,
      image: "https://images.unsplash.com/photo-1642427749670-f20e2e76ed8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=580&q=80",
    }
  ]
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
