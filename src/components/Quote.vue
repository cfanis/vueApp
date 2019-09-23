<template>
  <div class="quote">
    <br>
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
  props: {
    msg: String
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
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
