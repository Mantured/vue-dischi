<template>
  <div class="loader">
    <img
      src="../assets/images/loader.jpg"
      class="animate__animated animate__rotateOut rounded-circle"
    />
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Loader",
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
div.loader {
  .animate__animated {
    width: 300px;
    height: 300px;
    animation-duration: 10s;
    filter: opacity(0.6);
  }
}
</style>
