<template lang="html">
  <div class="main-container">
    <h1>Harry Potter</h1>
    <sorting-hat></sorting-hat>
    <!-- <p>{{characters}}</p> -->
    <!-- <p>{{spells}}</p> -->
  </div>
</template>

<script>
import SortingHat from './components/sortingHat'
export default {
  name: 'app',
  data(){
    return{
      characters: [],
      spells: []
    };
  },
  components: {
    'sorting-hat': SortingHat
  },

  mounted(){
    fetch("https://www.potterapi.com/v1/characters?key=$2a$10$wmc1QkABdgEulOcSMTdYz.qQgGJyMBJXVNoXNJu5428XykYmJCHW6")
    .then(response => response.json())
    .then(characters => this.characters = characters)

    fetch("https://www.potterapi.com/v1/characters?key=$2a$10$wmc1QkABdgEulOcSMTdYz.qQgGJyMBJXVNoXNJu5428XykYmJCHW6")
    .then(response => response.json())
    .then(spells => this.spells = spells)
  }
}
</script>

<style lang="css" scoped>
</style>
