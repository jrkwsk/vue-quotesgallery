<template>
  <div class="container">
    <app-header :quotesCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new @quoteAdded="newQuote"></app-new>
    <app-grid :quotes="quotes" @itemDeleted="deleteQuote"></app-grid>
    <div class="row text-center">
      <div class="alert alert-danger">click the quoute to delete it</div>
    </div>
  </div>
</template>

<script>
import Grid from "./components/Grid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  data: function() {
    return {
      quotes: ["one quote"],
      maxQuotes: 10
    };
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Reached max. Delete quotes first");
      }

      this.quotes.push(quote);
    },

    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appGrid: Grid,
    appNew: NewQuote,
    appHeader: Header
  }
};
</script>

<style>
body {
  font-family: "Amatic SC", cursive;
  font-size: 2rem;
  background-image: radial-gradient(circle, #5c0067 0%, #00d4ff 100%);
  color: white;
}
h3 {
  padding: 20px;
}
.alert {
  margin: 20px;
}
</style>
