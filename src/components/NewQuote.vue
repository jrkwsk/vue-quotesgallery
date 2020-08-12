<template>
  <div class="row">
    <form action>
      <div class="col-6">
        <h3 for>Enter a new quote here:</h3>
        <textarea name id cols="60" rows="10" v-model="quote"></textarea>
        <button class="btn btn-primary" @click.prevent="addNew">Add</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      quote: ""
    };
  },
  methods: {
    addNew() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style scoped>
textarea {
  width: 100%;
  color: darkslateblue;
}
</style>