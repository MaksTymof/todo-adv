<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
body{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background-image: url('../public/img/nasa-rTZW4f02zY8-unsplash.jpeg');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 100vh;
}

#nav {
  padding: 30px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  a {
    font-weight: bold;
    color: #2c3e50;
    display: block;
    margin: 0 auto;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
