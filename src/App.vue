<template>
  <div id="app">
    <header-main @search="searchAll" />
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
    return { filterAll: [], movieArray: [], tvShowArray: [] };
  },
  methods: {
    searchAll: function (keyWord) {
      this.filterAll = [];
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?query=${keyWord}&api_key=3fbfc4b818bb0d4b8927c10be152c7b5&language=it`
        )
        .then((result) => {
          this.movieArray = result.data.results;
          this.movieArray.forEach((item) => {
            item.val = "movie";
            this.filterAll.push(item);
          });
        });

      axios
        .get(
          `https://api.themoviedb.org/3/search/tv?query=${keyWord}&api_key=3fbfc4b818bb0d4b8927c10be152c7b5&language=it`
        )
        .then((result) => {
          this.tvShowArray = result.data.results;
          this.tvShowArray.forEach((item) => {
            item.val = "tvShow";
            this.filterAll.push(item);
          });
        });
    },
  },
};
</script>

<style lang="scss">
@import "style/main.scss";
</style>
