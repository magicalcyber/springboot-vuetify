<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
import axios from "axios";

const AXIOS = axios.create({
  baseURL: "http://localhost:8081/",
  timeout: 10000,
});

export default {
  name: "HelloWorld",
  data() {
    return {
      msg: String
    }
  },
  mounted() {
    this.sayHello()
  },
  methods: {
    sayHello() {
      AXIOS.get("/hello/magickiat").then(
        (response) => (this.msg = response.data)
      );
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
