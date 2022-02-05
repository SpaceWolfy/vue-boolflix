<template>
  <div id="app">
    <div class="LoginPage" v-show="show">
      <h1>Bentornato XxSuperDevxX!</h1>
      <h2>Seleziona il tuo account</h2>
      <div
        @click="
          show = false;
          hide = true;
        "
        class="box-account"
      ></div>
    </div>

    <div class="MainPage" v-show="hide">
      <header-main @search="search" />
      <main-section
        :movies="movieArray"
        :shows="tvShowArray"
        :trending="trendingArray"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import HeaderMain from "./components/HeaderMain.vue";
import MainSection from "./components/MainSection.vue";

export default {
  name: "App",
  components: {
    HeaderMain,
    MainSection,
  },
  data() {
    return {
      show: true,
      hide: false,
      movieArray: [],
      tvShowArray: [],
      trendingArray: [],
      apiKey: "3fbfc4b818bb0d4b8927c10be152c7b5",
    };
  },
  mounted() {
    axios
      .get(`https://api.themoviedb.org/3/movie/popular?api_key=${this.apiKey}`)
      .then((res) => {
        for (let i = 0; i < 15; i++) {
          this.trendingArray.push(res.data.results[i]);
        }
      });
  },

  methods: {
    search(querySearch) {
      if (querySearch !== "") {
        this.searchAMovie(querySearch);
        this.searchAShow(querySearch);
      } else {
        this.movieArray = [];
        this.tvShowArray = [];
      }
    },

    async searchAMovie(movieQuery) {
      this.movieArray = await this.serverCall("movie", movieQuery);
    },

    async searchAShow(showQuery) {
      this.tvShowArray = await this.serverCall("tv", showQuery);
    },

    async serverCall(type, query) {
      const params = {
        query: query,
        api_key: this.apiKey,
        language: "it",
      };

      const results = await axios
        .get(`https://api.themoviedb.org/3/search/${type}`, { params })
        .then((result) => {
          console.log("HO RISPOSTO", result.data.results);
          if (result.data.total_results === 0) {
            return alert("La tua ricerca non ha prodotto risultati");
          } else {
            return result.data.results;
          }
        });

      return results;
    },
  },
};
</script>

<style lang="scss">
@import "style/main.scss";

.LoginPage {
  height: 100vh;
  background-color: black;
  display: flex;
  flex-direction: column;
  justify-content: center;
  color: white;
  align-items: center;

  h1 {
    font-size: 40px;
    margin-bottom: 30px;
  }

  .box-account {
    margin-top: 30px;
    height: 130px;
    width: 130px;
    background-color: rebeccapurple;
    background-image: url("https://mir-s3-cdn-cf.behance.net/project_modules/disp/bb3a8833850498.56ba69ac33f26.png");
    background-size: cover;
    border-radius: 20px;
    cursor: pointer;

    &:hover {
      height: 150px;
      width: 150px;
      transition: 0.5s;
      border-radius: 30px;
    }
  }
}
</style>
