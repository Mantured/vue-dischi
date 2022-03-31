<template>
  <nav class="navbar navbar-light px-2">
    <a class="navbar-brand" href="#">
      <img src="../assets/images/logo.svg" alt="logo spotify" />
    </a>
    <select class="form-select my-size" aria-label="Default select example">
      <option selected>Open this select menu</option>
      <option value="1">One</option>
      <option value="2">Two</option>
      <option value="3">Three</option>
    </select>
  </nav>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Header",
  props: {},
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
    width: 20%;
  }
}
</style>
