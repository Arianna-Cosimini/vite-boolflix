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

    <div class="container mb-4">
        <h3>I film</h3>
        <div class="cards d-flex flex-wrap">

            <CardsItem v-for="currentFilm in store.filmList" :imageCard="currentFilm.poster_path"
                :titleFilm="currentFilm.title" :originalTitle="currentFilm.original_title"
                :language="currentFilm.original_language"
                :vote="currentFilm.vote_average">
            </CardsItem>
        </div>

    </div>

    <div class="container mb-4">
        <h3>Le serie</h3>
        <div class="cards d-flex flex-wrap">
            <CardsItem v-for="currentSerie in store.series" :imageCard="currentSerie.poster_path"
                :titleSerie="currentSerie.name" :originalName="currentSerie.original_name"
                :language="currentSerie.original_language"
                :vote="currentSerie.vote_average">
            </CardsItem>

        </div>

    </div>

</template>

<style lang="scss"></style>