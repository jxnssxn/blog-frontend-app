<template>
<div class="container">
  <div class="posts-index">
    <h1>{{ message }}</h1>
    <div v-for="post in posts">
      <p>{{ post.title }}</p>
       <p><img v-bind:src="post.image" v-bind:alt="post.title"></p>
       <p>{{post.body}}</p>
    </div>
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
    console.log("posts index");

    this.postIndex();
  },
  methods: {
    postIndex: function () {
      console.log("posts index");
      axios.get("api/posts").then((response) => {
        console.log(response.data);
        this.posts = response.data;
      });
    },
  },
};
</script>