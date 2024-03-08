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


    },

    name: ' CardsItem',


}

</script>

<template>


    <div id="image" class="card">

        <div class="card-img">
            <img v-if="imageCard !== null" :src="'https://image.tmdb.org/t/p/w342' + imageCard" alt="">


            <img v-else src="../../public/img/Fashion Minimal Mascot Logo.svg" alt="">

        </div>



        <div class="card-body">

            <h5 class="card-title">{{ titleFilm }}</h5>
            <h6 class="card-subtitle mb-2 text-body-secondary">{{ originalTitle }}</h6>
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

            <div class="vote">
                <p>
                    <span v-for="star in 5"
                        :class="{ 'fas fa-star': vote >= star, 'far fa-star': vote < star }">
                    </span>
                </p>
            </div>

        </div>

    </div>



</template>

<style lang="scss" scoped>
.card {
    width: calc(100% / 5);
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
    }

    .flag {
        img {
            width: 50px;
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
</style>