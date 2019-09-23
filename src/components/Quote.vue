<template>
  <div class="quote">
    <h3> {{ quote }} </h3>
    <br>
    <button type="button" @click="loadQuote">Random Ron Swanson Quote!</button>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'Quote',
  data () {
    return {
      quote: null
    }
  },
  created: function() {
    this.loadQuote()
  }, 
  methods: {
    loadQuote : function () {
      axios
        .get('https://ron-swanson-quotes.herokuapp.com/v2/quotes/', "Accept: application/json")
        .then(response => (this.quote = response.data[0]))
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
button {
  color: #42b983;
}
</style>
