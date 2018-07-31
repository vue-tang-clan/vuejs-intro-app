<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <input type="text" v-model="message">
    <h2>{{ message2 }}</h2>
    <h1>Reviews</h1>
    <ul>
      <li v-for="review in reviews">
        {{ review.rating }}: {{ review.text }} - by {{ review.reviewer }}
      </li>
    </ul>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!!!",
      message2: "yo",
      reviews: [
        { text: "Vue.js is cool", rating: 5, reviewer: "Burton Wax" },
        { text: "Vue.js is great", rating: 4, reviewer: "Emily Post" },
        { text: "I like checkers", rating: 1, reviewer: "Angela Pearson" }
      ]
    };
  },
  created: function() {},
  methods: {},
  computed: {}
};
</script>
