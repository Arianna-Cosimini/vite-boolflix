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

    <ul>
        <li v-for="currentFilm in store.filmList">
        {{ currentFilm.original_title }}</li>
    </ul>


    
</template>

<style lang="scss">

</style>