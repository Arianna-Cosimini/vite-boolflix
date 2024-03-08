<script>
import { store } from '../store.js';


export default {

    data() {
        return {
            store,
        }
    },

    props: {

        imageCard: String,
        titleFilm: String,
        titleSerie: String,
        originalTitle: String,
        originalName: String,
        language: String,


    },

    name: ' CardsItem',


}

</script>

<template>
    <div class="container">
        <div class="cards d-flex flex-wrap">

            <div class="card">

                <div class="card-body">

                    <img :src="'https://image.tmdb.org/t/p/w342' + imageCard" alt="">

                    <h5 class="card-title">{{ titleFilm }}</h5>
                    <h6 class="card-subtitle mb-2 text-body-secondary">{{ originalTitle }}</h6>
                    <div class="flag">

                        <img v-if="language == 'en'" src="../../public/img/british-flag-.jpg"
                            alt="English Flag">
                        <img v-else-if="language == 'it'"
                            src="../../public/img/italy-italia-flag-of-italy-italian-flag-flag.webp" alt="Italian Flag">
                        <img v-else-if="language == 'fr'" src="../../public/img/fr.png"
                            alt="French Flag">
                        <img v-else-if="language == 'es'"
                            src="../../public/img/illustration-of-spain-flag-vector.jpg" alt="Spain Flag">
                        <img v-else-if="language == 'cn'" src="../../public/img/cn-flag.jpg"
                            alt="Italian Flag">
                        <img v-else-if="language == 'sv'" src="../../public/img/swiss02_flag.jpg"
                            alt="Italian Flag">

                        <img v-else src="../../public/img/Fashion Minimal Mascot Logo.svg" alt="">


                    </div>

                </div>

            </div>

        </div>




        <!-- <div class="cards d-flex flex-wrap">

            <div class="card">

                <div class="card-body">
                    <img :src="'https://image.tmdb.org/t/p/w300' + imageCard" alt="">

                    <h5 class="card-title">{{titleSerie }}</h5>
                    <h6 class="card-subtitle mb-2 text-body-secondary">{{ originalName }}</h6>
                    <p class="card-text">{{ currentSerie.overview }}</p>
                    <p class="card-text">{{ currentSerie.vote_average }}</p>
                </div>

            </div>

        </div> -->

    </div>

</template>

<style lang="scss" scoped>

.card{
    width: calc(100% / 5);

    img{
        width: 100%;
        // height: 100%;
        object-fit: cover;
    }

    .flag{
        img{
            width: 50px;
        }
    }
}


</style>