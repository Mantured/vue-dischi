<template>
  <div id="app">
    <Header @select="selectGenre" @search="searchArtist" />
    <Cards :selectToInput="selectToInput" :selectToSearch="selectToSearch" />
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
  data: function () {
    return {
      selectToInput: "",
      selectToSearch: "",
    };
  },
  methods: {
    selectGenre(value) {
      console.log(value);
      this.selectToInput = value;
      console.warn(this.selectToInput);
    },
    searchArtist(search) {
      console.warn(search);
      this.selectToSearch = search;
      console.log(this.selectToSearch);
    },
  },
};
</script>

<style lang="scss">
@import "/node_modules/bootstrap/scss/bootstrap.scss";
@import "./assets/scss/style.scss";

#app {
  background-color: $Container;
  height: 100vh;
  overflow: auto;
}
</style>
