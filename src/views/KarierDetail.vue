d
<template>
  <div class="karier-detail">
    <Banner></Banner>
    <SearchBar></SearchBar>
    <div
      class="detail-card__information"
      v-for="job in filterByCategory"
      :key="job.id"
    >
      <div class="left-side">
        <div class="description">
          <h2>Description</h2>
          <ul v-for="desc in job.data[id - 1].jobdescription" :key="desc.id">
            <li>{{ desc }}</li>
          </ul>
        </div>
        <div class="requirements">
          <h2>Requirements</h2>
          <ul v-for="req in job.data[id - 1].requirements" :key="req.id">
            <li>{{ req }}</li>
          </ul>
        </div>
      </div>
      <div class="right-side">
        <h1>{{ job.data[id - 1].position }}</h1>
        <span>{{ job.data[id - 1].location }}</span>
        <span>{{ job.data[id - 1].jobtype }}</span>
        <Button
          btnType="primary block"
          text="Lamar Sekarang"
          style="margin-bottom: 10px"
          path="/#"
        ></Button>
        <hr />
        <div class="social-media">
          <h3>Share</h3>
          <div class="img__wrapper">
            <img src="../assets/facebook.png" />
            <img src="../assets/twitter.png" />
            <img src="../assets/whatsapp.png" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Banner from "@/components/Banner.vue";
import SearchBar from "@/components/SearchBar.vue";
import Button from "@/components/Button.vue";
import joblists from "../data/joblists.json";

export default {
  name: "KarierDetail",
  components: {
    Banner,
    Button,
    SearchBar,
  },
  data() {
    return {
      data: joblists,
      category: this.$route.params.category,
      id: this.$route.params.id,
    };
  },
  computed: {
    filterByCategory() {
      return this.data.filter((job) => {
        return job.category.toLowerCase().includes(this.category.toLowerCase());
      });
    },
  },
};
</script>

<style scoped>
.karier-detail .detail-card__information {
  padding: 0 5em 5em;
  display: flex;
  flex-direction: row;
  align-items: flex-start;
}

.karier-detail .left-side,
.right-side {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  width: 100%;
  margin: 20px;
  padding: 20px;
  border-radius: 25px;
  position: relative;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
  transition: all 0.3s ease-in-out 0s;
}

.left-side {
  width: 50%;
}
.right-side {
  width: 50%;
  height: 100%;
}

.right-side span {
  font-weight: 600;
  color: #e28f17;
  line-height: 2;
}

.left-side div {
  margin: 50px;
}

.left-side h2 {
  margin-bottom: 20px;
}

hr {
  width: 100%;
  margin: 20px 0px;
  border-top: 1px solid rgb(238, 238, 238);
}

.social-media .img__wrapper {
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.social-media img {
  width: 30px;
  margin: 10px 20px;
}
</style>
