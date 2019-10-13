<template lang="html">
  <div class="form">
    <p class="sorting-hat-intro">Do you want to join Harry and his friends? <br>
    Enter your detials and find out which house you'll be a part of...</p>
    <form @submit.prevent>
      <input class="name-input" v-model="name" placeholder="Name" type="text" name="" value="">
      <p>Pick your pet: </p>
      <div class="radio-buttons">
        <input v-model="picked" type="radio" name="pet" value="Cat" id="Cat"><label for="Cat">Cat</label><br>
        <input v-model="picked" type="radio" name="pet" value="Owl" id="Owl"><label for="Owl">Owl</label><br>
        <input v-model="picked" type="radio" name="pet" value="Newt" id="Newt"><label for="Newt">Newt</label><br>
        <input v-model="picked" type="radio" name="pet" value="Rat" id="Rat"><label for="Rat">Rat</label><br>
        <br>
      </div>
      <button @click="sortIntoHouse" type="button" name="button">Sort into House</button>
    </form>
    <div class="congratulations">

    </div>
    <div v-if="message.length" class="message">
      {{ message }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'sorting-hat',

  data(){
    return{
      sortingHat: "",
      picked: "",
      name: "",
      message: ""
    }
  },
  methods: {
    sortIntoHouse(){
      this.message = `Congratulations ${this.name} you and your ${this.picked} have been selected to join ${this.sortingHat}!! We look forward to welcoming you to Hogwarts School of witchcraft and wizardy`
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

  .form {
    margin: 0 auto;
    text-align: center;
    display: flex;
    justify-content: center;
    flex-direction: column;
    width: 500px;
  }
  .radio-buttons {
    display: flex;
    flex-direction: row;
    justify-content: center;
  }
  button {
    font-size: 15px;
    width: 40%;
    margin-right: 0;
    margin-bottom: 30px;
    padding: 15px;
    background-color: #241f61;
    color: white;
  }
  label {
    padding-left: 3px;
    padding-right: 25px;
  }
  .name-input {
    width: 45%;
    height: 20px;
    font-size: 15px;
  }
  .sorting-hat-intro {
    display: flex;
  }

  p {
    font-size: 22px;
  }

  .message {
    background-color: #241f61 ;
    padding: 30px;
    margin: 30px;
    font-size: 22px;
    color: white;
  }
  </style>
