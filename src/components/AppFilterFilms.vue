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
    <div class="container bg-dark">

        <div class="cards d-flex flex-wrap">

            <div v-for="currentFilm in store.filmList" class="card">

                <div class="card-body">
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
.card-body {}

.card {
    width: calc(100% / 5);

}
</style>