<template lang="html">
  <select v-on:change="handleSelectFilm" v-model="selectedFilmTitle">
    <option value="" disabled>
      {{ films.length ? 'Please select a film...' : 'Loading films...' }}
    </option>

    <option
      v-for="(film, index) in films"
      :key="index"
      :value="film.title">{{ film.title }}</option>
  </select>
</template>

<script>
import { eventBus } from '@/main.js';
export default {
  name: 'film-select',
  props: ['films', 'selectedFilmTitle'],
  data() {
    return {
      selectedFilmTitle: this.selectedFilmTitle
    };
  },
  methods: {
    handleSelectFilm() {
      eventBus.$emit('film-selected', this.selectedFilmTitle);
    }
  }
}
</script>

<style lang="css" scoped>
select {
  display: block;
}
</style>
