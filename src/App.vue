<template>
  <div id="app">
    <header-main />
    <main-section />
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
    return { moviesFilter: [] };
  },
  methods: {
    searchAMovie: function (movieName) {
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?query=${movieName}_key=3fbfc4b818bb0d4b8927c10be152c7b5`
        )
        .then((result) => {
          this.moviesFilter = result.data.results;
        });
    },
  },
};
</script>

<style lang="scss">
@import "style/main.scss";
</style>
