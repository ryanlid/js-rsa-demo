<template>
  <div id="app">
    <h1 class="text-center">JavaScript RSA 加密解密</h1>
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

h1 {
  font-size: 1.5em;
}
.text-center {
  text-align: center;
}

.box {
  display: flex;
  justify-content: space-around;
  width: 100%;
}

.box-item {
  width: 48%;
}

textarea {
  width: 100%;
}

.btn {
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
  box-sizing: border-box;
  padding: 6px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 1.42857143;
  text-align: center;
  white-space: nowrap;
  vertical-align: middle;
  cursor: pointer;
  user-select: none;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 4px;
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
  outline: none;
  margin-left: 10px;
}

.lib-statement {
  display: inline-block;
  padding: 10px;
  border: 1px solid #ddd;
  margin: 10px 0 10px 50%;
  transform: translateX(-50%);
}

a {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  color: #0000ee;
}
</style>
