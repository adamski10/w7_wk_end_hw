<template>
 <div>
    <div id="quote">
      <p>{{ quote.quote }}</p>
    </div>
    <div id="author">
      <p>{{ quote.author}}</p>
    </div>
 </div>

    
  
</template>

<script>
  import {eventBus} from '../main.js'
  export default {
    name: 'quote',
    props: ['quote'],
    methods: {
      handleClick(){
        eventBus.$emit('quote-selected', this.quote)
      }
  }
  }
  
</script>

<style>
  li {
    list-style: none;
  }
  
</style>