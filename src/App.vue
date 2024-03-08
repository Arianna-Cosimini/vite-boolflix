<script>
import axios from 'axios';

import { store } from './store.js';

import AppMain from './components/AppMain.vue'

import AppNavBar from './components/AppNavBar.vue'


export default {

  components: {
    AppMain,
    AppNavBar,

  },


  data() {
    return {

      store,

    }
  },

  created() {

  },

  mounted() {
    // richiamo il metodo per i film popolari, in questo modo 
    // li stampo in pagina al caricamento
    this.searchFilms();
  },


  methods: {
    // chiamata api per film popolari
    searchFilms() {
      axios
        .get(`https://api.themoviedb.org/3/movie/popular?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT`)
        .then(res => {

          console.log(res.data.results);
          this.store.popularFilms = res.data.results;

          console.log(this.store.popularFilms);

        });
    },
    // chiamata api per film ricercati dall'utente

    searchUser() {
      axios
        .get(`https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=${this.store.userChoice}`)
        .then(res => {

          // per ogni elemento dell'array converto il voto decimale in un massimo di 5
          res.data.results.forEach(film => {
            film.vote_average = Math.min(Math.ceil(film.vote_average / 2), 5);

          });
          console.log(res.data.results);
          this.store.filmList = res.data.results;

        });

      // chiamata api per serie ricercate dall'utente
      axios
        .get(`https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=${this.store.userChoice}`)
        .then(res => {
          res.data.results.forEach(film => {
            // per ogni elemento dell'array converto il voto decimale in un massimo di 5

            film.vote_average = Math.min(Math.ceil(film.vote_average / 2), 5);

          });
          console.log(res.data.results);
          this.store.series = res.data.results;

        });

    },

  }
}
</script>

<template>
  <AppNavBar @search="searchUser()"></AppNavBar>


  <AppMain></AppMain>


</template>

<style></style>