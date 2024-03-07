<script>
import axios from 'axios';

import { store } from './store.js';

import AppForm from './components/AppForm.vue';
import AppFilterFilms from './components/AppFilterFilms.vue'

export default {

  components: {
    AppForm,
    AppFilterFilms,
  },


  data() {
    return {
     
      store,

    }
  },

  created() {
    this.searchFilms() 
  },

  mounted() {

  },


  methods: {

    searchFilms() {
      axios
        .get(`https://api.themoviedb.org/3/movie/popular?api_key=e99307154c6dfb0b4750f6603256716d&language=it`)
        .then(res => {
          console.log(res.data.results);
          this.store.filmList = res.data.results;
          
        });
    },

    searchUser(){
      axios
        .get(`https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&language=it&query=${this.store.userChoice}`)
        .then(res => {
          console.log(res.data.results);
          this.store.filmList = res.data.results;
          
        });
    }
}
}
</script>

<template>
 <AppForm @search="searchUser()"></AppForm>
 <AppFilterFilms></AppFilterFilms>

</template>

<style></style>