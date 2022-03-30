<template>
  <div id="app">
    <Header />
    <Cards />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Cards from "./components/Cards.vue";

export default {
  name: "App",
  components: {
    Header,
    Cards,
  },
};
</script>

<style lang="scss">
@import "/node_modules/bootstrap/scss/bootstrap.scss";
@import "./assets/scss/style.scss";
/*  */
</style>
