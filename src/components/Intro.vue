<template>
  <body>
   <h1 v-on:click="goToOptions"><i>Quotes worth knowing </i></h1>
  </body>
</template>

<script>
export default {
  name: 'intro',

  mounted(){
    goToOptions = eventBus.$on
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