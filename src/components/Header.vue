<template>
  <nav class="navbar navbar-light px-2">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <a class="navbar-brand" href="#">
            <img src="../assets/images/logo.svg" alt="logo spotify" />
          </a>
        </div>
      </div>
      <div class="row justify-content-center">
        <div class="col-10 d-flex align-items-center">
          <select v-model="selectInput" class="form-select my-size">
            <option @click="$emit('select', selectInput)" value="">All</option>
            <option
              v-for="genre in genresList"
              :key="genre"
              :value="genre"
              @click="$emit('select', selectInput)"
            >
              {{ genre }}
            </option>
            <!-- <option value>Select kind of disc</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option> -->
          </select>
          <div class="container">
            <div class="d-flex">
              <input
                class="form-control me-2"
                type="search"
                placeholder="Search"
                v-model.trim="searchInput"
                @keydown="newEvent"
                @keyup.enter="$emit('search', searchInput)"
              />
              <!-- "$emit('search', searchInput)" -->
              <button
                @click="$emit('search', searchInput)"
                class="btn btn-outline-success"
                type="submit"
              >
                Search
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
/* import axios from "axios"; */
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Header",
  props: {},
  data: function () {
    return {
      selectInput: "",
      searchInput: "",
      genresList: ["Rock", "Pop", "Jazz", "Metal"],
    };
  },
  /* created: function () {
    this.getGenresList();
  }, */
  methods: {
    /* getGenresList() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          this.genresList = result.data.response;
          console.log(this.genresList);
        })
        .catch((error) => {
          console.error(error);
        });
    }, */
    newEvent() {
      if (this.searchInput === "") {
        console.warn("nessuna richerca");
        this.searchInput = "";
      } else {
        this.$emit("search", this.searchInput);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
nav {
  background-color: $Grey;
  a img {
    width: 100%;
    height: 7vh;
  }
}
</style>
