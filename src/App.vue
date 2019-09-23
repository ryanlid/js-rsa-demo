<template>
  <div id="app">
    <div class="text-center">
      <router-link to="/">Home</router-link> |
      <router-link to="/rsaencrypt">rsaencrypt</router-link> |
      <router-link to="/node-rsa">node-rsa</router-link> |
      <a href="/jsencrypt.html">jsencrypt</a>
    </div>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.text-center {
  text-align: center;
}
</style>
