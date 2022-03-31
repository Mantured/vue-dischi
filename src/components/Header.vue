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
      <p class="text-danger">
        selezionato :
        {{ selectInput }} - {{ searchInput }}
      </p>
      <div class="row justify-content-center">
        <div class="col-10 d-flex align-items-center">
          <select
            v-model="selectInput"
            @click="$emit('select', selectInput)"
            class="form-select my-size"
            aria-label="Default select example"
          >
            <option value>Select kind of disc</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
          </select>
          <div class="container">
            <form class="d-flex">
              <input
                class="form-control me-2"
                type="search"
                placeholder="Search"
                v-model="searchInput"
                @keyup.down="$emit('search', searchInput)"
              />
              <button class="btn btn-outline-success" type="submit">
                Search
              </button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Header",
  props: {},
  data: function () {
    return {
      selectInput: "",
      searchInput: "",
    };
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
  select.my-size {
  }
}
</style>
