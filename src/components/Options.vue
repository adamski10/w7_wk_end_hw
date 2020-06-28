<template>
  <div class="options">
    <p>Favourites</p>
    <p>Categories</p>
    <p>Authors</p>
    <p v-on:click="inspireMeClick()">Inspire me</p>
    <p v-on:click="stoicismClick()">Stoicism</p>
    <p v-on:click="mysticismClick()">Mystycism</p>
    <p v-on:click="existentialismClick()">Existentialism</p>
    <p>Uplifiting</p>
  </div>
</template>

<script>
import { eventBus } from '../main'
import Quotes from '../App'
export default {
  name: 'options',
  props: ['quote'],
  methods: {
    inspireMeClick() {
      eventBus.$emit('inspire-me')
    },
    stoicismClick(){
      eventBus.$emit('stoicism')
    },
    mysticismClick(){
      eventBus.$emit('mysticism')
    },
    existentialismClick(){
      eventBus.$emit('existentialism')
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