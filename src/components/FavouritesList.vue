<template>
  <div id="favourites">
    <h1>My favourite ones</h1>
    <ul>
      <li v-for="(quote,index) in favourites" :key="index">
        <p>{{quote.quote}}</p>
        <i>Author: {{quote.source}}</i>
      </li>
      
    </ul>
  </div>
</template>

<script>
import {eventBus} from '../main.js'
export default {
  name:'fav-list',
  props:['quote'],

  data(){
    return {
      favourites: []
    }
  },

  mounted() {
    eventBus.$on('favourite-quote', quote => {
      if(!this.favourites.includes(quote))
      this.favourites.push(quote);
    })
  }


}
</script>

<style scoped>
  #favourites {
    
    background-color: rgb(233, 230, 230);
  }

  ul {
    list-style-type: none;
    display: flex;
    flex-direction: row;
    border: 1px solid black;
    border-radius: 25px;
    flex-wrap: wrap;
    max-height: 50%;
    align-items: center;
    justify-content: space-evenly;
  }

  li {
    border: 1px solid black;
    border-radius: 25px;
    max-width: 30%;
  }
</style>