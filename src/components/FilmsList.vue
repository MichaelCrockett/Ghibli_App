<template lang="html">
  <div>
    <ul>
      <list-item v-for="(film, index) in films" :film="film" :key="index"></list-item>
    </ul>
  </div>

</template>

<script>
import ListItem from './ListItem.vue';

export default {
  name: 'films-list',
  props: ['films'],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped> {
  background-color: wheat;
  border-style: solid;
  border-color: saddlebrown;
  margin: 10px;
  padding: 10px;
}

list-item {
  background-color: wheat;
  border-style: solid;
  border-color: saddlebrown;
  margin: 10px;
  padding: 10px;
  max-width: 60%;
}


ul {
  list-style-type: none;
  font-size: 30px;
}

</style>
