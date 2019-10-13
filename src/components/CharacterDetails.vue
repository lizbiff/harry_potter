<template lang="html">
  <div class="character-details" v-if="selectedCharacter">
    <h3>Characters name: {{selectedCharacter.name}}</h3>
    <h3>House: {{selectedCharacter.house}}</h3>
    <h3>Member of Dumblodores Army?: {{ selectedCharacter.dumbledoresArmy ? '✅' : '🚫' }}</h3>
    <h3>Worked for Ministry of Magic?: {{ selectedCharacter.ministryOfMagic ? '✅' : '🚫' }}</h3>
    <h3>Role: {{selectedCharacter.role}}</h3>
    <h3>Member of the Order of the Phoenix: {{ selectedCharacter.orderOfThePhoenix ? '✅' : '🚫' }}</h3>

    <!-- <button @click="addedFav" type="button" name="button">Add to Favourite beers</button> -->

  </div>
</template>

<script>
import { eventBus } from '../main'
export default {
  name: 'character-detail',
  props: ['selectedCharacter'],
  // methods:{
  //   addedFav(){
  //     // need to push this beer into favBeers
  //     eventBus.$emit('favourited-beer', this.selectedBeer)
  //   }
  // }
}
</script>

<style lang="css" scoped>
.character-details {
  display: flex;
  text-align: center;
  width: 400px;
  background-color: #241f61;
  margin: 0 auto;
  flex-direction: column;
  color: white;

}
</style>
