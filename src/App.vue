<template>
  <div id="app">
    <div id="nav">
      <img alt="Vue logo" src="./assets/logo.png" />
      <router-link to="/">Tujuan Kami</router-link>
      <router-link to="/karier">Lowongan Kerja</router-link>
      <router-link to="/#our-value">Nilai-Nilai Kompas</router-link>
      <router-link to="/#activity">Keseharian Kami</router-link>
      <router-link to="/#aboutus">Mengenal Kami</router-link>
    </div>
    <router-view />
  </div>
</template>

<script>
/* When the user scrolls down, hide the navbar. When the user scrolls up, show the navbar */
var prevScrollpos = window.pageYOffset;
window.onscroll = function () {
  var currentScrollPos = window.pageYOffset;
  if (prevScrollpos > currentScrollPos) {
    document.getElementById("nav").style.top = "0";
  } else {
    document.getElementById("nav").style.top = "-100px";
  }
  prevScrollpos = currentScrollPos;
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#nav {
  padding: 30px;
  background-color: #ffffff;
  top: 0;
  width: 100%;
  display: flex;
  justify-content: center;
  position: fixed;
  z-index: 10;
  box-shadow: rgba(0, 0, 0, 0.45) 0px 10px 30px -15px;
  transition: top 0.3s;
}

#nav a {
  font-weight: bold;
  color: #111827;
  text-decoration: none;
  margin: 20px;
}

#nav img {
  width: auto;
  height: 100%;
  display: block;
  margin: auto 50px;
}

#nav a:hover {
  color: #e28f17;
}
#nav a.router-link-exact-active {
  color: #e28f17;
}
</style>
