<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Shop</router-link>
      <router-link to="/about">Cart</router-link>
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
  display: flex;
  justify-content: space-between;
  padding: 2rem 4rem;
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
