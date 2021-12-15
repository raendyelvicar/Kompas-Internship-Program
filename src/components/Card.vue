<template>
  <div class="card-cust">
    <h2>{{ position }}</h2>

    <div class="card__information">
      <span>{{ location }}</span>
      <span>{{ jobtype }}</span>
    </div>

    <hr />

    <Button
      btnType="detail"
      text="Lihat Detail"
      style="margin-bottom: 10px"
      :path="`/karier/detail/` + category + `/` + id"
    ></Button>
    <Button btnType="primary" text="Lamar Sekarang"></Button>
  </div>
</template>

<script>
import Button from "./Button.vue";

export default {
  name: "Card",
  components: {
    Button,
  },
  props: {
    id: String,
    category: String,
    position: String,
    location: String,
    jobtype: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card-cust {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  padding: 20px;
  height: 300px;
  width: 100%;
  border-radius: 25px;
  position: relative;
  text-align: center;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
  transition: all 0.3s ease-in-out 0s;
}

.card-cust:hover {
  transform: translateY(-5px);
}

.card-cust h2 {
  text-align: left;
  min-height: 30px;
  display: -webkit-box;
  font-weight: 800;
  line-height: 1.5em;
  margin: 0px 0px 10px;
  height: 3em;
  font-size: 1.182em;
  text-overflow: ellipsis;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-transform: capitalize;
}

.card__information {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  text-align: left;
}

.card__information span {
  margin-right: 50px;
  color: #e28f17;
}

hr {
  width: 100%;
  margin: 20px 0px;
  border-top: 1px solid rgb(238, 238, 238);
}
</style>
