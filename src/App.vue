<template>
  <div>
    <h1>The films of Studio Ghibli</h1>
    <div class="main-container">
      <!-- <form>
        <film-select
        :selectedFilmTitle="selectedFilmTitle"
        :films="films">
      </film-select>
    </form> -->
    <film-detail :film='selectedFilm'></film-detail>
    <films-list :films='films'></films-list>
  </div>
</div>
</template>

<script>
import FilmsList from './components/FilmsList.vue';
import FilmDetail from './components/FilmDetail.vue';
import FilmSelect from './components/FilmSelect.vue'
import { eventBus } from './main.js';

export default {
  name: 'app',
  data(){
    return {
      films: [],
      selectedFilm: null
    };
  },
  mounted(){
    fetch('https://ghibliapi.herokuapp.com/films/')
    .then(res => res.json())
    .then(films => this.films = films)

    eventBus.$on('film-selected', (film) => {
      this.selectedFilm = film
    })
  },
  components: {
    "films-list": FilmsList,
    "film-detail": FilmDetail,
    "film-select": FilmSelect,
  }
}
</script>

<style>
.main-container {
  background-color: cornsilk;
  opacity: 0.8;
  border-style: solid;
  border-color: saddlebrown;
  margin: 10px;
  padding: 10px;
  font-family: fantasy;
}

h1  {
  text-align: center;
  background-color: cornsilk;
  border-style: solid;
  border-color: saddlebrown;
  margin: 10px;
  padding: 10px;
  font-family: Verdana;
  font-size: 40px;
  align-content: center;
  margin-top: 30px

}

body {
  background-image: url(./assets/ghibli_collage.png);
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center top;
  background-size: cover;


}
</style>
