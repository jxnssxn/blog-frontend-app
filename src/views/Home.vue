<template>
  <div class="home">
    <h1>{{ message }}</h1>
     <div v-for="post in posts">
       <h3> {{post.title}} </h3>
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
      message: "Welcome to the blog!",
      posts: [],
    };
  },
  created: function () {
    this.postIndex();
  },
  methods: {
    postIndex: function () {
      console.log("home is printing");
      axios.get("/api/posts").then((response) => {
        console.log(response.data);
      });
    },
  },
};
</script>