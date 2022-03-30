<template>
  <div id="app">
    <Navbar />
    <Cards />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Cards from "./components/Cards.vue";

export default {
  name: "App",
  components: {
    Navbar,
    Cards,
  },
};
</script>

<style lang="scss">
/*  */
</style>
