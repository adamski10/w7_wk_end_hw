<template>
   <div v-if='quote !== null'> 
    <h2>Author: {{quote.source}}</h2>
    <h4>Category: {{quote.philosophy}}</h4>
    <h5>{{quote.quote}}</h5>
   </div>
</template>

<script>
export default {
  name: 'quote-details',
  props: ['quote']
}
</script>

<style>

</style>