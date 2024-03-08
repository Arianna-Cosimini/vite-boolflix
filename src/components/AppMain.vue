<script>
import { store } from '../store.js';
import CardsItem from './CardsItem.vue';



export default {

    data() {
        return {
            store,
        }
    },

    name: 'AppMain',

    components: {
        CardsItem,
    },


}

</script>


<template>
    <!-- I film popolari -->
    <div class="container mb-4" v-if="store.popularFilms && store.popularFilms.length > 0">
        <h3>I più popolari</h3>
        <div class="cards d-flex flex-wrap">
            <!-- tramite v-for genero i film popolari-->

            <CardsItem v-for="film in store.popularFilms" :key="film.id" :imageCard="film.poster_path"
                :titleFilm="film.title" :originalTitle="film.original_title" :language="film.original_language"
                :vote="film.vote_average" :overview="film.overview">
            </CardsItem>
        </div>
    </div>

    <!-- I film richiesto dall'utente -->
    <div class="container mb-4" v-if="store.filmList.length > 0">

        <h3>I film</h3>
        <div class="cards d-flex flex-wrap">
            <!-- tramite v-for genero i film corrispondenti alla richiesta dell'utente -->
            <CardsItem v-for="currentFilm in store.filmList" :imageCard="currentFilm.poster_path"
                :titleFilm="currentFilm.title" :originalTitle="currentFilm.original_title"
                :language="currentFilm.original_language" :vote="currentFilm.vote_average"
                :overview="currentFilm.overview">
            </CardsItem>
        </div>

    </div>

<!--Le serie richieste dall'utente  -->
    <div class="container mb-4" v-if="store.series.length > 0">
        <h3>Le serie</h3>
        <div class="cards d-flex flex-wrap">

            <!-- tramite v-for genero le serie corrispondenti alla richiesta dell'utente -->

            <CardsItem v-for="currentSerie in store.series" :imageCard="currentSerie.poster_path"
                :titleSerie="currentSerie.name" :originalName="currentSerie.original_name"
                :language="currentSerie.original_language" :vote="currentSerie.vote_average"
                :overview="currentSerie.overview">
            </CardsItem>

        </div>

    </div>


</template>

<style lang="scss"></style>