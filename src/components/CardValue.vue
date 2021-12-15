<template>
  <div class="card-value">
    <img :alt="value" :src="require(`@/assets/value/` + filename)" />
    <h2>{{ value }}</h2>
    <p>{{ description }}</p>
  </div>
</template>

<script>
export default {
  name: "CardValue",
  props: {
    filename: String,
    value: String,
    description: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card-value {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 20px;
  height: 350px;
  width: 100%;
  border-radius: 25px;
  position: relative;
  text-align: center;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
  transition: all 0.3s ease-in-out 0s;
}

.card-value:hover {
  transform: translateY(-5px);
}

.card-value h2 {
  text-align: left;
  min-height: 30px;
  display: -webkit-box;
  font-weight: 800;
  line-height: 1.5em;
  margin-bottom: 20px;
  font-size: 1.182em;
  text-overflow: ellipsis;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-transform: capitalize;
}

.card-value p {
  text-align: left;
}
</style>
