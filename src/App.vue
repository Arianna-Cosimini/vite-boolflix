<script>
import axios from 'axios';

import { store } from './store.js';

import AppForm from './components/AppForm.vue';
import AppFilterFilms from './components/AppFilterFilms.vue'
import AppFilterSeries from './components/AppFilterSeries.vue'
import AppNavBar from './components/AppNavBar.vue'


export default {

  components: {
    AppForm,
    AppFilterFilms,
    AppNavBar,
    AppFilterSeries,
  },


  data() {
    return {
     
      store,

    }
  },

  created() {
    
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
        .get(`https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=${this.store.userChoice}`)
        .then(res => {
          console.log(res.data.results);
          this.store.filmList = res.data.results ;
          
        });

        axios
        .get(`https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=${this.store.userChoice}`)
        .then(res => {
          console.log(res.data.results);
          this.store.series = res.data.results;
          
        });
    }
}
}
</script>

<template>
  <AppNavBar @search="searchUser()"></AppNavBar>
 <AppFilterFilms>
  
 </AppFilterFilms>

 <AppFilterSeries></AppFilterSeries>

</template>

<style></style>