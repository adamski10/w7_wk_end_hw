<template>
 <div v-if='quote !== null'>
    <div id="quote">
      <p><i>"{{ quote.quote }}"</i></p>
    </div>
    <div id="author">
      <p>{{ quote.source}}</p>
    </div>
    <button v-on:click="addToFavourites">Add to Fav List</button> 
    
 </div>

</template>

<script>
  import {eventBus} from '../main.js'
  export default {
    name: 'quote',
    props: ['quote'],
    methods:{
      addToFavourites() {
        eventBus.$emit('favourite-quote', this.quote)
      }
    }
  }
  
</script>

<style scoped>
  
  
</style>