<script>
import { store } from '../store.js';


export default {

    data() {
        return {
            store,
        }
    },

    name: 'AppFilterSeries',


}

</script>

<template>
    <div class="container">

        <h1>le serie</h1>

        <div class="cards d-flex flex-wrap">

            <div v-for="currentSerie in store.series" class="card">

                <div class="card-body">
                    <img :src="'https://image.tmdb.org/t/p/w300' + currentSerie.poster_path" alt="">

                    <h5 class="card-title">{{ currentSerie.name }}</h5>
                    <h6 class="card-subtitle mb-2 text-body-secondary">{{ currentSerie.original_name }}</h6>
                    <p class="card-text">{{ currentSerie.overview }}</p>
                    <p class="card-text">{{ currentSerie.vote_count }}</p>
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