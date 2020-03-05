<template>
  <div class="hello">
    <h1>Jokes</h1>
    <p></p>
    <button @click="showJoke()">Show Info</button>
    <div v-if="joke"></div>
    <p>{{joke}}</p>
  </div>
</template>

<script>
import axios from "axios";


export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return { joke: "" }
  },
  methods: {
    // showJoke() {
    //   alert("Hello world");
    // }

async showJoke(){
      let config = {headers: {'Accept': 'application/json'
    }
  };
  var joke = await axios.get('https://icanhazdadjoke.com', config);
  this.joke = joke.data.joke
}}}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
