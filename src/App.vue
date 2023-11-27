<script>
import Header from './components/AppHeader.vue';
import Main from './components/AppMain.vue';

export default {
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
