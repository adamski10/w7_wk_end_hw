<template>
 <div v-if='quote !== null'>
    <div id="quote">
      <p><i>"{{ quote.quote }}"</i></p>
    </div>
    <div id="author">
      <p>{{ quote.source}}</p>
    </div>
 </div>

</template>

<script>
  
  export default {
    name: 'quote',
    props: ['quote'],

    methods: {
      
    }
   
   
  }
  
</script>

<style>
  li {
    list-style: none;
  }
  
</style>