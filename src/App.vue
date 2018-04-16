<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-image: url("./assets/bg.jpg");
  -webkit-background-size: cover;
  background-size: cover;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right:0;
  }
</style>
