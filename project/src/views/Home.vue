<template>
  <div class="home">
    <h1>{{now}}</h1>
    <button v-on:click="authState" v-if="loggedIn">{{status[0]}}</button>
    <button @click="authState" v-else>{{status[1]}}</button>
    <ul>
      <li v-for="animal in animals" :key="animal">{{animal}}</li>
    </ul>
    <input type="text" placeholder="type here" v-model="message">
    <p>{{message}}</p>
    <input type="checkbox" id="jack" value="jack" v-model="checkedNames">
    <label for="jack">jack</label>
    <input type="checkbox" id="john" value="john" v-model="checkedNames">
    <label for="john">john</label>
    <input type="checkbox" id="mike" value="mike" v-model="checkedNames">
    <label for="mike">mike</label>
    <br>
    <span>Checked names: {{checkedNames}}</span>
    <br>
    <select v-model="selected">
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>
    <br>
    <span>{{selected}}</span>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {},
  data() {
    return {
      status: ["logout", "login"],
      loggedIn: false,
      animals: ["dog", "cat", "pig", "cow", "hen"],
      message: "",
      checkedNames: [],
      selected: "",
    }
  },
  computed: {
    now: function () {
      const time = new Date(); 
      return `${time.getHours()}:${time.getMinutes()}`
    }
  }, 
  methods: {
    authState: function () {
      if(this.loggedIn===false) {
        this.loggedIn = true;
      } else {
        this.loggedIn = false
      }
    }
  }
}
</script>

<style>
  button {
    background-color: #151515;
    color: #fff;
    border: none;
    border-radius: 0.2rem;
    height: 2rem;
    width: 5rem;
    font-size: 1rem;
    transition: all 0.3s;
  }

  button:hover {
    background-color: rgba(21, 21, 21, 0.7);
    cursor: pointer;
  }

  li {
    list-style: none;
  }
</style>
