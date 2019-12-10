<template>
  <div>
        <slot v-bind:quote="quote">
        </slot>
  </div>
</template>
<script>
export default {
  data() {
    return {
      quote: '', 
      loading: false,
      errors: []
    };
  },
  methods: {
    async getQuote() {
      this.loading = true;
      const response = await fetch('https://favqs.com/api/qotd')
      const result = await response.json();
      setTimeout(function(){ }, 3000);
      this.quote = result.quote;
      this.$emit('quoteofday', result.quote);
      this.loading = false;
    }
  },
  async mounted() {
    this.getQuote();
  }
};
</script>
<style></style>
