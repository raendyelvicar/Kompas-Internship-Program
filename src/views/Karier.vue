<template>
  <div class="karier">
    <Banner></Banner>
    <SearchBar></SearchBar>
    <div
      class="card__container"
      v-for="items in content.body"
      v-bind:key="items.id"
    >
      <h2>{{ items.category }}</h2>
      <div class="card__wrapper">
        <Card
          v-for="item in items.data"
          v-bind:key="item.id"
          v-bind:id="item.id"
          v-bind:category="items.category"
          v-bind:position="item.position"
          v-bind:location="item.location"
          v-bind:jobtype="item.jobtype"
        ></Card>
      </div>
      <hr />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Card from "@/components/Card.vue";
import Banner from "@/components/Banner.vue";
import SearchBar from "@/components/SearchBar.vue";
import joblists from "../data/joblists.json";

export default {
  name: "Karier",
  components: {
    Card,
    Banner,
    SearchBar,
  },
  data() {
    return {
      content: {
        body: joblists,
      },
    };
  },
};
</script>

<style scoped>
.card__container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: left;
  width: 80%;
  margin: auto;
}

.card__container h2 {
  font-weight: 800;
  line-height: 1.5em;
  font-size: 1.5em;
}

.card__container h2::after {
  content: "";
  height: 5px;
  width: 5%;
  background: #e28f17;
  position: relative;
  display: block;
}
.card__wrapper {
  width: 100%;
  margin: auto;
  margin-top: 50px;
  margin-bottom: 50px;
  display: -ms-grid;
  display: grid;
  -ms-grid-columns: (minmax(300px, 1fr)) [auto-fit];
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  -webkit-column-gap: 20px;
  column-gap: 20px;
  row-gap: 20px;
}

hr {
  width: 100%;
  margin: 20px 0px;
  border-top: 1px solid rgb(238, 238, 238);
}
</style>
