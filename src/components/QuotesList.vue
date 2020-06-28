<template>
  <div>
    <quote v-for="(quote,index) in quotes"  :quote="quote" :key="index"></quote>
    <button v-on:click="back">Take me back</button>
  </div>

</template>

<script>
import Quote from './Quote'


export default {
  name: 'QuotesList',
  props: ['quotes'],
  components: {
    "quote": Quote
  },

  methods: {
      back(){
        window.location.reload()
      }
    }

}
</script>

<style>

</style>

