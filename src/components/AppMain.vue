<script>
import { store } from '../store.js';
import CardsItem from './CardsItem.vue';



export default {

    data() {
        return {
            store,
        }
    },

    name: 'AppMain',

    components: {
        CardsItem,
    },


}

</script>


<template>
<CardsItem></CardsItem>
</template>

<style lang="scss">


</style>