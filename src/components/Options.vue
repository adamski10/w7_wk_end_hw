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
    background-color: rgb(12, 11, 11);
  }

  p {
    justify-content: space-evenly;
    align-content: space-around;
    padding: 50px;
    margin: 100px;
    width: 100px;
    border: 1px solid gray;
    border-radius: 25px;
    color: blanchedalmond;
  }
</style>