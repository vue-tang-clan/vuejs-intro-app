<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <input type="text" v-model="message">
    <h2>{{ message2 }}</h2>
    <h1>Add a review</h1>
    Review text: <input type="text" v-model="newReview.text">
    Review rating: <input type="text" v-model="newReview.rating">
    Review name: <input type="text" v-model="newReview.reviewer">
    <button v-on:click="addReview()">Add review</button>

    <h1>Reviews</h1>
    <ul>
      <li v-for="review in reviews" v-on:click="deleteReview(review)">
        <div v-if="review.text.indexOf('bad') === -1">
          {{ review.rating }}: {{ review.text }} - by {{ review.reviewer }}
        </div>
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
        { text: "I like checkers", rating: 1, reviewer: "Angela Pearson" },
        { text: "Vue.js is bad", rating: 1, reviewer: "Vishnu No Please" }
      ],
      newReview: { text: "", rating: "", reviewer: "" }
    };
  },
  created: function() {},
  methods: {
    addReview: function() {
      console.log("nice...", this.newReview);
      if (this.newReview.text) {
        this.reviews.push(this.newReview);
        this.newReview = { text: "", rating: "", reviewer: "" };
      }
    },
    deleteReview: function(inputReview) {
      console.log("deleteReview...", inputReview.text);
      var index = this.reviews.indexOf(inputReview);
      this.reviews.splice(index, 1);
    }
  },
  computed: {}
};
</script>
