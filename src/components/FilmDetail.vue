<template lang="html">
  <div class="filmdetails" v-if='film'>
    <h2>{{film.title}}</h2>
    <p><b>Directed by:</b> {{film.director}}</p>
    <p><b>Released:</b> {{film.release_date}}</p>
    <p><b>Description: </b> {{ film.description }}</p>
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

.filmdetails {
background-color: white;
border-style: solid;
border-color: saddlebrown;
padding: 10px
}



</style>
