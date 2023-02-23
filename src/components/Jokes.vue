<template>
    <div class="row jokes">
      <div class="col-md-4" v-for="(joke, index) in jokes" :key="index">
        <div class="card">
          <div class="card-body">
            <h2 class="card-text">{{ joke.setup }}</h2>
            <br>
            <h3 class="card-text">{{ joke.punchline }}</h3>
            <button class="btn btn-primary" @click="fetchJokes">Reload</button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import axios from "axios";
  
  export default {
    name: "JokesCard",
    data() {
      return {
        jokes: [],
      };
    },
    methods: {
      fetchJokes() {
        axios.get("https://official-joke-api.appspot.com/jokes/general/random").then((response) => {
          this.jokes = response.data;
        });
      },
    },
    mounted() {
      this.fetchJokes();
    },
  };
  </script>

  <style scoped>

  .jokes {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: end;

  }
  h3 {
    font-weight: bolder;
  }

  button {
    background-color: rgb(159, 0, 37);
  }


</style>
  