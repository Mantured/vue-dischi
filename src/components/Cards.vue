<template>
  <div>
    <main class="container-fluid">
      <div class="row">
        <div class="col-12 text-danger">
          <h1>{{ selectToInput }} - {{ selectToSearch }}</h1>
        </div>
      </div>
      <div class="row p-5 justify-content-center" v-if="cardsList">
        <div
          class="col-12 col-sm-6 col-md-4 col-lg-2"
          v-for="(disc, index) in newInputValue(selectToInput)"
          :key="index"
        >
          <Card :discObj="disc" />
        </div>
      </div>
      <div class="row" v-else>
        <div class="col-12">
          <!-- <h1 class="loader text-danger">Loading...</h1> -->
          <Loader />
        </div>
      </div>
    </main>
  </div>
</template>

<script>
/* importo axios dopo averlo installato */
import axios from "axios";

import Card from "./Card.vue";
import Loader from "./Loader.vue";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Cards",
  props: {
    selectToInput: String,
    selectToSearch: String,
  },
  components: {
    Card,
    Loader,
  },
  data: function () {
    return {
      cardsList: null,
    };
  },
  created: function () {
    setTimeout(this.getApiElement, 1);
  },
  methods: {
    getApiElement() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          this.cardsList = result.data.response;
        })
        .catch((error) => {
          console.error(error);
        });
    },
    newInputValue(stringValue) {
      console.log(stringValue);
      return this.cardsList.filter((element) =>
        element.genre.includes(stringValue)
      );
    },
    newSearchInput(stringSearch) {
      console.log(stringSearch);
      return this.cardsList.filter((element) =>
        element.genre.includes(stringSearch)
      );
    },
  },
};
</script>

<style style lang="scss" scoped>
@import "../assets/scss/style.scss";
main {
  .loader {
    height: 93vh; //! lol
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
