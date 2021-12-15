<template>
  <div class="quotes">
    <div class="quotes__wrapper">
      <img src="../assets/quotes-2.png" />
      <div class="text__wrapper">
        <p class="quotes__text">
          "Bekerja dalam bidang apapun sesungguhnya adalah interaksi, kombinasi
          yang kreatif antara intelek dan hati."
        </p>
        <p class="quotes__text">- Jakob Oetama</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Quotes",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.quotes {
  height: 40vh;
  position: relative;
  overflow: hidden;
  margin-bottom: 100px;
  background-image: url("../assets/quotes-bg.png");

  /* Position and center the image to scale nicely on all screens */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  z-index: 1;
}

.quotes__wrapper {
  width: 80%;
  display: flex;
  flex-direction: row;
  align-items: center;
  margin: auto;
}

.quotes img {
  width: 20%;
  height: auto;
  margin-right: 20px;
}

.quotes__text {
  font-size: 24px;
  font-weight: 800;
  color: #333;
}
</style>
