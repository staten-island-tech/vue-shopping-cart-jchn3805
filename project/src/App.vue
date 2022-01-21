<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #151515;
}

#nav {
  padding: 2rem;
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
</style>
