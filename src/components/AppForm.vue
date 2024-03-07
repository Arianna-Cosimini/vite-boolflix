<script>
import { store } from '../store.js';


export default {

    data() {
        return {
            store,
        }
    },

    name: 'AppForm',


}

</script>

<template>
    <div class="container">

        <form class="w-100 d-flex align-items-center justify-content-center bg-transparent">
    
                <input v-model="store.userChoice" type="text" class="form-control" id="exampleInputEmail1" placeholder="Scegli un film" aria-describedby="emailHelp">
            
            <button @click="$emit('search')" type="button" class="btn btn-primary">invia</button>
        </form>
    </div>

</template>

<style lang="scss"></style>