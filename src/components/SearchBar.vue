<template>
  <div class="search-bar">
    <form class="form-inline">
      <select id="location" name="location">
        <option value="Jakarta">Jakarta</option>
        <option value="Yogyakarta">Yogyakarta</option>
        <option value="Bandung">Bandung</option>
      </select>

      <input
        type="text"
        id="position"
        placeholder="Masukkan posisi yang dicari"
      />

      <Button type="submit" btnType="primary" text="Cari"></Button>
      <span>atau</span>
      <Button btnType="primary" text="Lihat Semua Posisi"></Button>
    </form>
  </div>
</template>

<script>
import Button from "./Button.vue";

export default {
  name: "SearchBar",
  components: { Button },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.form-inline {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  width: 100%;
}

.search-bar {
  margin: auto;
  padding: 20px;
  display: flex;
  flex-direction: row;
  align-items: center;
  position: absolute;
  top: 60%;
  left: 50%;
  transform: translate(-50%, -40%);
  width: 90%;
  border-radius: 25px;
  background: #ffffff;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
  transition: all 0.3s ease-in-out 0s;
  z-index: 10;
}

select#location {
  width: 200px;
}

input#position {
  width: 400px;
  margin: 0 20px;
}

input[type="text"],
select {
  vertical-align: middle;
  width: 100%;
  padding: 10px 20px;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  color: #2c3e50;
  font-size: 16px;
}

input[type="text"]:focus,
select:focus {
  border: 1px solid #e28f17;
  box-shadow: 0 0 3px #e28f17;
  outline-offset: 0px;
  outline: none;
}

.search-bar span {
  margin: 20px;
}
</style>
