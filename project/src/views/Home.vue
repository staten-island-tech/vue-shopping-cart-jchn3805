<template>
  <div class="home">
    <h1 v-if="login">{{status[1]}}</h1>
    <h1 v-else>{{status[0]}}</h1>
    <ul>
      <li v-for="animal in animals" :key="animal">{{animal}}</li>
    </ul>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data() {
    return {
      status: ["login", "logout"],
      login: false,
      animals: ["dog", "cat", "pig", "cow", "hen"]
    }
  }
}
</script>
