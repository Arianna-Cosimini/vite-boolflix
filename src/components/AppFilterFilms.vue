<script>
import { store } from '../store.js';


export default {

    data() {
        return {
            store,
        }
    },

    name: 'AppFilterFilms',


}

</script>

<template>
    <div class="container">

        <!-- <h1>I più popolari</h1> -->

        <div class="cards d-flex flex-wrap">

            <div v-for="currentFilm in store.filmList" class="card">

                <div class="card-body">
                    <img :src="'https://image.tmdb.org/t/p/w342' + currentFilm.poster_path" alt="">

                    <h5 class="card-title">{{ currentFilm.title }}</h5>
                    <h6 class="card-subtitle mb-2 text-body-secondary">{{ currentFilm.original_title }}</h6>
                    <p class="card-text">{{ currentFilm.original_language }}</p>
                    <p class="card-text">{{ currentFilm.vote_count }}</p>
                </div>

            </div>

        </div>
    </div>



</template>

<style lang="scss">


.card {
    width: calc(100% / 5);

}
</style>