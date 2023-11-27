<script>
import Header from './components/AppHeader.vue';
import Selector from './components/AppSelector.vue';
import Main from './components/AppMain.vue';

export default {
  components: {
    Header,
    Selector,
    Main,
  }
}
</script>

<template>
  <Header/>
  <Selector/>
  <Main/>
</template>

<style lang="scss">
  @use "./style/general.scss";
</style>
