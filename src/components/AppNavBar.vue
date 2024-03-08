<script>
import { store } from '../store.js';


export default {

    data() {
        return {
            store,
        }
    },

    name: 'AppNavBar',


}

</script>

<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <div class="container-fluid align-items-center">
            <a class="navbar-brand" href="#">
                <img src="../../public/img/Fashion Minimal Mascot Logo.svg"alt="">
               

            
            </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="nav-link active" aria-current="page" href="#">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Serie tv</a>
                    </li>
                    
                    <li class="nav-item">
                        <a class="nav-link" href="#">Film</a>
                    </li>
                     
                    <li class="nav-item">
                        <a class="nav-link" href="#">Nuovi e popolari</a>
                    </li>
                     
                    <li class="nav-item">
                        <a class="nav-link" href="#">La mia lista</a>
                    </li>
                     
                    <li class="nav-item">
                        <a class="nav-link" href="#">Sfoglia per lingua</a>
                    </li>
                </ul>
                <form class="d-flex" role="search">
                    <input v-model="store.userChoice" class="border rounded pe-2 me-2" type="search" placeholder="Scegli un film" aria-label="Search">
                    <button @click="$emit('search')" class="btn btn-outline-light" type="button">Invia</button>
                </form>
            </div>
        </div>
    </nav>


</template>

<style lang="scss">


img{
    width: 150px;
}

</style>