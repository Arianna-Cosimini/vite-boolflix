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
        vote: Number,
        overview: String,


    },

    name: ' CardsItem',


}

</script>

<template>


    <div id="image" class="card">
        <!-- immagine principale della card -->
        <div class="card-img">
            <img v-if="imageCard !== null" :src="'https://image.tmdb.org/t/p/w342' + imageCard" alt="">
            <!-- controllo: se l'immagine non c'è la sostituisco -->
            <img v-else src="../../public/img/Fashion Minimal Mascot Logo.svg" alt="">

        </div>



        <div class="card-body p-1">

            <h6 class="card-title m-0">{{ titleFilm }}</h6>
            <span class="card-subtitle mb-2 text-body-secondary mb-2">{{ originalTitle }}</span>

            <!-- Sostituisco la lingia con le bandiere -->
            <div class="flag">

                <img v-if="language == 'en'" src="../../public/img/british-flag-.jpg" alt="English Flag">
                <img v-else-if="language == 'it'"
                    src="../../public/img/italy-italia-flag-of-italy-italian-flag-flag.webp" alt="Italian Flag">
                <img v-else-if="language == 'fr'" src="../../public/img/fr.png" alt="French Flag">
                <img v-else-if="language == 'es'" src="../../public/img/illustration-of-spain-flag-vector.jpg"
                    alt="Spain Flag">
                <img v-else-if="language == 'cn'" src="../../public/img/cn-flag.jpg" alt="Italian Flag">
                <img v-else-if="language == 'sv'" src="../../public/img/swiss02_flag.jpg" alt="Italian Flag">

                <img v-else src="../../public/img/Fashion Minimal Mascot Logo.svg" alt="">


            </div>

            <!-- sostituisco il voto con le stelle.  -->
            <div class="vote">

                <!-- ho utilizzato il v-for per generare un numero massimo di 5 stelle 
                dove il numero di stelle piene dipende dal valore di vote -->
                <p>
                    <span v-for="star in 5" :class="{ 'fas fa-star': vote >= star, 'far fa-star': vote < star }">
                    </span>
                </p>
            </div>

            <!-- Descrizione del film -->
            <div class="overview">
                <span>{{ overview }}</span>
            </div>

        </div>

    </div>



</template>

<style lang="scss" scoped>
.card {
    width: calc(100% / 6);
    background-color: #242424;


    .card-img {

        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

    }

    .card-body {
        position: absolute;
        top: 0;
        left: 0;
        opacity: 0;
        transition: opacity .3s;

        width: 100%;
        text-align: center;
    }

    .flag {
        img {
            width: 30px;
        }
    }

}


.card:hover {

    .card-body {
        opacity: 1;
    }

    .card-img {
        opacity: 0;
    }
}

.overview {
    line-height: 12px;

    span {
        font-size: 12px;
    }
}
</style>