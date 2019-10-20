<template lang="html">
  <div v-if='film'>
    <h3>{{film.title}}</h3>
    <p>Directed by: {{film.director}}</p>
    <p>Released: {{film.release_date}}</p>
  </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'film-detail',
  props: ['film']
}

</script>

<style lang="css" scoped>
</style>
