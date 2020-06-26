<template>
  <div class="options">
    <p>Favourites</p>
    <p>Favourites</p>
    <p>Favourites</p>
    <p>Favourites</p>
    <p>Favourites</p>
    <p>Favourites</p>
    <p>Favourites</p>
    <p>Favourites</p>
    <p>Favourites</p>
  </div>
</template>

<script>
export default {
  name: 'options'

}
</script>

<style scoped>
  .options {
    display: flex;
    flex-wrap: wrap;
  }

  p {
    justify-content: space-evenly;
    align-content: space-around;
    padding: 20px;
    margin: 100px;
  }
</style>