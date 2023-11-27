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

  created () {
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
    .then((resp) => {
      this.store.cards = resp.data.data;
      console.log(this.store);
    });
  },

  components: {
    Header,
    Main,
  }
}
</script>

<template>
  <Header/>
  <Main/>
</template>

<style lang="scss">
  @use "./style/general.scss";
</style>
