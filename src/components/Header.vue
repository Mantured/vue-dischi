<template>
  <nav class="navbar navbar-light px-2">
    <a class="navbar-brand" href="#">
      <img src="../assets/images/logo.svg" alt="logo spotify" />
    </a>
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
}
img {
  width: 100%;
  height: 7vh;
}
</style>
