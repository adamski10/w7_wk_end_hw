<template>
  <div id="app">
    <h1>Ciekawe cytaty znanych filozofów</h1>
    <quote-details :quote='selectedQuote'></quote-details>
    <ul>
      <quote v-for='(quote, index) in quotes' :key='index' :quote='quote'></quote>
    </ul>
    
  </div>
</template>

<script>
import quote from './components/quote'
import quoteDetails from './components/quoteDetails'
import {eventBus} from './main.js'

export default {
  name: 'App',
  data(){
    return {
      quotes: [],
      selectedQuote: null
    };
  },
  mounted(){
    fetch('http://philosophy-quotes-api.glitch.me/quotes')
    .then(res => res.json())
    .then(quotes => this.quotes = quotes)
    
    eventBus.$on('quote-selected', (quote) => {
      this.selectedQuote = quote
    })
  },
  components: {
    'quote': quote,
    'quote-details': quoteDetails
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

ul {
  display: flex;
  flex-direction: column-reverse;
  padding: 10px;
}

li {
  padding: 10px;
}


</style>
