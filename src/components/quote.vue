<template>
 
    <li v-on:click='handleClick'>{{ quote.quote }}</li>
    
  
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