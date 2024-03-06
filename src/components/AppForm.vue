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

        <form class="w-25">
            <div class="mb-3">
                <label for="exampleInputEmail1" class="form-label">Choose your film</label>
                <input type="text" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
                <div id="emailHelp" class="form-text"></div>
            </div>
            <button type="button" class="btn btn-primary">invia</button>
        </form>
    </div>

</template>

<style lang="scss"></style>