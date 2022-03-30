<template>
  <div class="card p-2 mb-2">
    <img
      class="card-img-top p-3 mb-2"
      :src="discObj.poster"
      :alt="discObj.title"
    />
    <div class="card-body text-center">
      <h5 class="card-title">{{ discObj.title }}</h5>
      <p class="card-text">{{ discObj.author }}</p>
      <p class="card-text">{{ discObj.year }}</p>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Card",
  props: { discObj: Object },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
div.card {
  background-color: $Grey;
  height: 430px;
  img {
    height: 100%;
  }
  h5 {
    color: white;
  }
  p {
    color: $SubText;
  }
}
</style>
