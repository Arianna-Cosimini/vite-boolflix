<script>
import axios from 'axios';

import { store } from './store.js';

import AppForm from './components/AppForm.vue';

export default {

  components: {
    AppForm,
  },


  data() {
    return {
     
      store,

    }
  },

  created() {
   
  },

  mounted() {

  },


  methods: {

   
}
}
</script>

<template>
 <AppForm></AppForm>

</template>

<style></style>