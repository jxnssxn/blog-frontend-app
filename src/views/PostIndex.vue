<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="post in posts">
      <p>{{ post }}</p>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Welcome to the post index page!",
      posts: [],
    };
  },
  created: function () {
    this.postIndex();
  },
  methods: {
    postIndex: function () {
      console.log();
      axios.get("/api/posts").then((response) => {
        console.log(response.data);
        this.posts = response.data;
      });
    },
  },
};
</script>
