<template lang="html">
  <div class="search-character">
    <h2>Search for a character you would you like to know more about?</h2>
    <!-- <label for="search-character">Search:</label>
    <input @change="changeSelect" list="searched-character-list" id="character-choice" />

    <datalist id="searched-character-list">
    <option v-for="(character, index) in characters">{{ character }}</option>
  </datalist> -->

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
    }
  }
}
</script>



<style lang="css" scoped>

.search-character {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: center;
  width: 400px;
  margin: 35px auto;
}
</style>
