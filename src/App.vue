<template>
  <div id="app">
    
    <options v-if='!selectedQuote' ></options>
    <div id="quote">
      <quote id="details" :quote='selectedQuote'></quote>
    </div>
    <ul>
      <!-- <quote v-for='(quote, index) in quotes' :key='index' :quote='quote'></quote> -->
    </ul>
    
  </div>
</template>

<script>

import Quote from './components/Quote'
import Options from './components/Options'
import {eventBus} from './main.js'

export default {
  name: 'App',
  data(){
    return {
      quotes: [],
      selectedQuote: null,
      selectedCategory: null
    };
  },
  
  mounted(){
    fetch('http://philosophy-quotes-api.glitch.me/quotes')
    .then(res => res.json())
    .then(quotes => this.quotes = quotes),
  

    eventBus.$on('category-selected', (quote) => {
      this.selectedQuote = this.quotes[Math.floor(Math.random() * this.quotes.length)]
       
    }),

    eventBus.$on('options', (options) => {

    })
  },
  components: {
    'options': Options,
    'quote': Quote
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

#quote {
  display: flex;
  flex-direction: column;
  align-items: center;
}

#details {
  background-color: rgb(201, 246, 212);
  border: 1px dimgrey;
  
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
