<template>
  <div id="app">
    <h1 id="title">Quotes worth reading...</h1>
    
    <options v-if='!selectedQuote && !selectedCategory' ></options>
    
    <quote :quote='selectedQuote'></quote>
    
    <QuotesList :quotes='selectedCategory'></QuotesList>

    <fav-list/>
    
    
  </div>
</template>

<script>
import QuotesList from './components/QuotesList'
import FavouritesList from './components/FavouritesList'
import Quote from './components/Quote'
import Options from './components/Options'
import {eventBus} from './main.js'

export default {
  name: 'App',
  data(){
    return {
      quotes: [],
      selectedQuote: null,
      selectedCategory: null,
      favourites: []
    };
  },
  
  mounted(){
    fetch('http://philosophy-quotes-api.glitch.me/quotes')
    .then(res => res.json())
    .then(quotes => this.quotes = quotes),
  

    eventBus.$on('inspire-me', () => {
      this.selectedQuote = this.quotes[Math.floor(Math.random() * this.quotes.length)]
    }),

    eventBus.$on('stoicism', () => {
      function stoicism(quote){
        return quote.philosophy === "Stoicism"
      }
      this.selectedCategory = this.quotes.filter(stoicism)
      
    }),

    eventBus.$on('mysticism', () => {
      function mysticism(quote){
        return quote.philosophy === "Mysticism"
      }
      this.selectedCategory = this.quotes.filter(mysticism)
      console.log(this.selectedCategory)
    }),

    eventBus.$on('existentialism', () => {
      function existentialism(quote){
        return quote.philosophy === "Existentialism"
      }
      this.selectedCategory = this.quotes.filter(existentialism)
      console.log(this.selectedCategory)
    })

  },

  components: {
    'options': Options,
    'quote': Quote,
    'QuotesList': QuotesList,
    'fav-list': FavouritesList
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
    background-color: rgb(233, 230, 230);
  }

  #title {
    background-color: rgb(233, 230, 230);
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
