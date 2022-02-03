<template>
  <div id="app">
    <header-main @search="searchAMovie" />
    <main-section :filterAll="filterAll" />
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
    return { filterAll: [] };
  },
  methods: {
    searchAll: function (movieName) {
      this.filterAll = [];
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?query=${movieName}&api_key=3fbfc4b818bb0d4b8927c10be152c7b5&language=it`
        )
        .then((result) => {
          this.filterAll = result.data.results;
        });

      axios
        .get(
          `https://api.themoviedb.org/3/search/tv?query=${movieName}&api_key=3fbfc4b818bb0d4b8927c10be152c7b5&language=it`
        )
        .then((result) => {
          this.filterAll = result.data.results;
        });
    },
  },
};
</script>

<style lang="scss">
@import "style/main.scss";
</style>
