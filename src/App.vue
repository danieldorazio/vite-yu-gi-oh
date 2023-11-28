<script>
import axios from "axios";
import Header from './components/AppHeader.vue';
import Main from './components/AppMain.vue';
import { store } from "./store.js";


export default {
  data() {
    return {
      store
    };
  },

  created() {
    this.store.loading = true;
    axios
      .get(this.store.apiUrl, {
        params: {
          num: this.store.numeroElementi,
          offset: this.store.paginaIniziale,
        },
    })
      .then((resp) => {
        this.store.cards = resp.data.data;
        console.log(this.store);
        this.store.loading = false;
      });
  },

  components: {
    Header,
    Main,
  }
}
</script>

<template>
  <Header />
  <Main />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>
