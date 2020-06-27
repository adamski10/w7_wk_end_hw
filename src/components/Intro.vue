<template>
  <body>
   <h1><i>Quotes worth knowing </i></h1>
  </body>
</template>

<script>
import Options from './Options';


export default {
  name: 'intro',

  
  methods: {
      
  },

  components: {
    'options': Options
  }

}
</script>

<style scoped>
  body {
    background-color: black;
  }

  h1 {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    color: cornsilk;
  }
</style>