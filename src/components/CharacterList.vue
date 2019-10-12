<template lang="html">
  <div class="">
    <h2>Who would you like to know more about?</h2>
    <select @change="changeSelect" v-model="characterSelected">
      <option disabled value="">Select character</option>
      <option v-for="(character, index) in characters" :value="character">{{ character.name }}</option>
    </select>
  </div>
</template>

<script>
import CharacterOption from './CharacterOption'
import { eventBus } from '../main'
export default {
  name: 'characters-list',
  props: ['characters'],
  data: () => ({
    characterSelected: ""
  }),
  components: {
    CharacterOption
  },
  methods: {
    changeSelect() {
      eventBus.$emit('character-selected',
      this.characterSelected);
      console.log(this.characterSelected)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
