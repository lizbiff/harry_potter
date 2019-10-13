<template lang="html">
  <div class="main-container">
    <h1>Harry Potter Fan Zone</h1>
    <character-list :characters="characters"></character-list>
    <character-detail :selectedCharacter="selectedCharacter"></character-detail>
    <sorting-hat />
    <!-- <p>{{characters}}</p> -->
    <!-- <p>{{spells}}</p> -->
  </div>
</template>

<script>
import { eventBus } from './main'
import SortingHat from './components/SortingHat'
import CharacterList from './components/CharacterList'
import CharacterDetail from './components/CharacterDetails'
export default {
  name: 'app',
  data(){
    return{
      characters: [],
      spells: [],
      selectedCharacter: null
    };
  },
  components: {
    SortingHat,
    CharacterDetail,
    CharacterList
  },

  mounted(){
    fetch("https://www.potterapi.com/v1/characters?key=$2a$10$wmc1QkABdgEulOcSMTdYz.qQgGJyMBJXVNoXNJu5428XykYmJCHW6")
    .then(response => response.json())
    .then(characters => this.characters = characters)




    eventBus.$on('character-selected', (selectedCharacter) =>{
      this.selectedCharacter = selectedCharacter;
    });
  }
}
</script>

<style lang="css">

.main {
}

.main-container {
  font-family: 'Mountains of Christmas', cursive;
  border-style: solid;
  border-width: 5

  px;
  border-color: #611f25;

}

h1 {
  display: flex;
  justify-content: center;
  font-size: 45px;
  font-weight: bold;
}



</style>
