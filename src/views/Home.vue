<template>
  <div class="home">
    <Banner></Banner>
    <SearchBar></SearchBar>
    <h1 style="text-align: center">Tujuan Kami</h1>
    <section id="about-us">
      <div class="about__content">
        <img src="../assets/about-us.png" />
        <div class="content-body">
          <h2 class="mb-8">Bekerja dengan Tujuan Baik</h2>
          <p class="mb-8">
            Lahir sejak tahun 1965, Harian Kompas terus konsisten untuk
            memberikan arah dan tujuan untuk Indonesia. Di tengah maraknya
            disrupsi dan krisis global, Harian Kompas tetap setia dengan
            idealismenya untuk mencerdaskan bangsa. Munculnya Kompas.id juga
            menjadi tanda transformasi Harian Kompas menjawab kebutuhan digital
            masyarakat.
          </p>
          <p class="mb-8">
            Dengan bergabung bersama Kompas, berarti Anda turut peduli pada
            kemajuan Indonesia. Di Harian Kompas, bekerja tidak hanya untuk
            kesejahteraan pribadi, tetapi juga untuk kepentingan orang banyak.
            Di Kompas, bekerja tidak terasa seperti bekerja, karena semua
            dijalani bersama layaknya keluarga sendiri.
          </p>
          <p class="mb-8">
            Sejalan dengan nilai “Amanat Hati Nurani Rakyat”, Kompas percaya
            bahwa bangsa Indonesia punya potensi yang besar untuk bersaing,
            dimulai dari rakyat, untuk rakyat.
          </p>
        </div>
      </div>
    </section>
    <section id="quotes">
      <Quotes></Quotes>
    </section>

    <h1 style="text-align: center">Nilai-Nilai Kompas</h1>
    <section id="our-value">
      <CardValue
        v-for="item in content.body"
        v-bind:key="item.id"
        v-bind:filename="item.filename"
        v-bind:value="item.value"
        v-bind:description="item.description"
      >
      </CardValue>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import Banner from "@/components/Banner.vue";
import Quotes from "@/components/Quotes.vue";
import CardValue from "@/components/CardValue.vue";
import SearchBar from "@/components/SearchBar.vue";
import kompasvalue from "../data/kompasvalue.json";

export default {
  name: "Home",
  components: { Banner, SearchBar, Quotes, CardValue },
  data() {
    return {
      content: {
        body: kompasvalue,
      },
    };
  },
};
</script>

<style scoped>
#about-us {
  display: flex;
  flex-direction: column;
  width: 80%;
  margin: auto;
  margin-bottom: 100px;
}

#about-us h1 {
  text-align: center;
}

.mb-8 {
  margin-bottom: 2rem;
  width: 80%;
}

.about__content {
  display: flex;
  flex-direction: row-reverse;
  justify-content: center;
  align-items: center;
}

#our-value {
  width: 80%;
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
</style>
