<template lang="html">
  <li>
    <span @click="detailIsVisible = !detailIsVisible">{{character.name}}</span>
    <p>{{character.role}}</p>
  </li>
</template>

<script>
export default {
  name: "character-option",
  props: ['character'],
  data: () => ({
    detailIsVisible: false
  })
}
</script>

<style lang="css" scoped>
</style>
