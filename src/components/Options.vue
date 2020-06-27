<template>
  <div class="options">
    <p>Favourites</p>
    <p>Categories</p>
    <p>Authors</p>
    <p v-on:click="handleClick()">Inspire me</p>
    <p >Stoicism</p>
    <p>Mystycism</p>
    <p>Existentialism</p>
    <p>Uplifiting</p>
  </div>
</template>

<script>
import { eventBus } from '../main'
export default {
  name: 'options',
  methods: {
    handleClick(category) {
      eventBus.$emit('category-selected', category)
    }
  }

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