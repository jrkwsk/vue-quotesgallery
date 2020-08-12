<template>
  <div class="row">
    <h3>List of your fav quotes</h3>
    <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote">{{quote}}</app-quote>
  </div>
</template>

<script>
import Quote from "./Quote.vue";
export default {
  props: ["quotes"],
  components: {
    appQuote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("itemDeleted", index);
    }
  }
};
</script>

<style>
</style>