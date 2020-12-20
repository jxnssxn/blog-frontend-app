

<template>
  <div class="home">
    <h1>{{ message }}</h1>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Welcome to the edit page!",
    };
  },
  created: function () {},
  // methods: {
  //    submit: function() {
  //     var params = {
  //       user_id: this
  // },
};
</script>