<template>
  <div class="banner"></div>
</template>

<script>
export default {
  name: "Banner",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.banner {
  height: 60vh;
  position: relative;
  overflow: hidden;
  margin-bottom: 100px;
  background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url("../assets/banner-img.jpg");

  /* Position and center the image to scale nicely on all screens */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  z-index: 1;
}
</style>
