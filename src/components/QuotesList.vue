<template>
  <div>
    <quote v-for="(quote,index) in quotes"  :quote="quote" :key="index"></quote>
  </div>

</template>

<script>
import Quote from './Quote'

export default {
  name: 'QuotesList',
  props: ['quotes'],
  components: {
    "quote": Quote
  }

}
</script>

<style>

</style>