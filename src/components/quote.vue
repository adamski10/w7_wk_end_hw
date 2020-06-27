<template>
 <div v-if='quote !== null'>
    <div id="quote">
      <p><i>"{{ quote.quote }}"</i></p>
    </div>
    <div id="author">
      <p>{{ quote.source}}</p>
    </div>
    <button v-on:click="back">Take me back</button>
 </div>

</template>

<script>
  
  export default {
    name: 'quote',
    props: ['quote'],

    methods: {
      back(){
        window.location.reload()
      }
    }
   
   
  }
  
</script>

<style scoped>
  
  
</style>