<template>
  <div id="app">
    <header-main @search="search" />
    <main-section :movies="movieArray" :shows="tvShowArray" />
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
      movieArray: [],
      tvShowArray: [],
      apiKey: "3fbfc4b818bb0d4b8927c10be152c7b5",
    };
  },
  mounted() {},

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
</style>
