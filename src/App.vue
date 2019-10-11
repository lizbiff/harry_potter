<template lang="html">
  <div class="main-container">
    <h1>Harry Potter</h1>
    <h3>{{sortingHat}}</h3>
    <!-- <p>{{characters}}</p> -->
    <!-- <p>{{spells}}</p> -->
  </div>
</template>

<script>
export default {
  name: 'app',
  data(){
    return{
      sortingHat: "",
      characters: [],
      spells: []
    };
  },

  mounted(){
    fetch("https://www.potterapi.com/v1/sortinghat")
    .then(response => response.json())
    .then(sortingHat => this.sortingHat = sortingHat)

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
