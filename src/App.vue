<template>
  <div id="app">
    <h1><intro/></h1>
    <options/>
    <quote-details id="details" :quote='selectedQuote'></quote-details>
    <ul>
      <!-- <quote v-for='(quote, index) in quotes' :key='index' :quote='quote'></quote> -->
    </ul>
    
  </div>
</template>

<script>
import Intro from './components/Intro'
import Quote from './components/Quote'
import Options from './components/Options'
import QuoteDetails from './components/QuoteDetails'
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
    .then(quotes => this.quotes = quotes),
  

    eventBus.$on('quote-selected', (quote) => {
      this.selectedQuote = quote
    }),

    eventBus.$on('options', (options) => {

    })
  },
  components: {
    'quote': Quote,
    'quote-details': QuoteDetails,
    'intro': Intro,
    'options': Options
  }
}
</script>

<style>
#app {
  display: grid;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#details {
  background-color: wheat;
  border: 1px solid green;
  max-width: 30%;
}

ul {
  display: flex;
  flex-direction: column-reverse;
  padding: 10px;
}

li {
  padding: 20px;
  margin: 10px 10px;
}


</style>
