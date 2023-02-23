<template>
  <div id="app">
    <jokes />
  </div>
</template>

<script>
import Jokes from "./components/Jokes.vue";

export default {
  name: "App",
  components: {
    Jokes,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100vh;
  background-color: rgb(255, 85, 212);
}
</style>