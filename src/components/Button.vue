<template>
  <div class="button">
    <a :class="['btn', btnType]" :href="path">{{ text }}</a>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    btnType: String,
    text: String,
    path: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.btn {
  padding: 10px 50px 10px;
  border-radius: 5px;
  font-weight: 600;
  cursor: pointer;
  text-decoration: none;
  width: 100%;
  display: block;
  text-align: center;
}

.primary {
  background: #e28f17;
  color: #fff;
}

.detail {
  color: #e28f17;
}
</style>
