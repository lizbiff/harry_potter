<template lang="html">
  <div class="">
    <form>
      <input v-model="name" placeholder="Name" type="text" name="" value="">
      <p>Pick your pet: </p>
      <input v-model="picked" type="radio" name="pet" value="Cat"><label for="Cat">Cat</label><br>
      <input v-model="picked" type="radio" name="pet" value="Owl"><label for="Owl">Owl</label><br>
      <input v-model="picked" type="radio" name="pet" value="Newt"><label for="Newt">Newt</label><br>
      <input v-model="picked" type="radio" name="pet" value="Rat"><label for="Rat">Rat</label><br>
      <br>
      <button @click="sortIntoHouse" type="button" name="button">Sort into House</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'sorting-hat',

  data(){
    return{
      sortingHat: "",
      personsHouse: []
    }
  },
  method:{
    sortIntoHouse(){

    }

  },

  mounted(){
    fetch("https://www.potterapi.com/v1/sortinghat")
    .then(response => response.json())
    .then(sortingHat => this.sortingHat = sortingHat)
  }
}


</script>

<style lang="css" scoped>
</style>
