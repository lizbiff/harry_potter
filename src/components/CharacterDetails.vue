<template lang="html">
  <div v-if="selectedCharacter">
    <h3>Characters name: {{selectedCharacter.name}}</h3>
    <h3>Role: {{selectedCharacter.role}}</h3>
    <h3>House: {{selectedCharacter.house}}</h3>

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
</style>
