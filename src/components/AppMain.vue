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
    <CardsItem v-for="currentFilm in store.filmList" 
    :imageCard="currentFilm.poster_path"
    :titleFilm="currentFilm.title"
    :originalTitle="currentFilm.original_title"
    :language="currentFilm.original_language">
    </CardsItem>

    <!-- <CardsItem v-for="currentSerie in store.series" 
    :imageCard="currentSerie.poster_path"
    :titleSerie="currentSerie.name"
    :originalName="currentSerie.original_name"
    :language="currentSerie.original_language">
    </CardsItem> -->
</template>

<style lang="scss"></style>