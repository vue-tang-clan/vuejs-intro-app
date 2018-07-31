<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <input type="text" v-model="message">
    <h2>{{ message2 }}</h2>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!!!",
      message2: "yo"
    };
  },
  created: function() {},
  methods: {},
  computed: {}
};
</script>
