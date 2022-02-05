<template>
  <div class="main" v-if="movies.length !== 0 || shows.length !== 0">
    <!-- <card-template v-for="obj in movies" :key="obj.id" :obj="obj" /> -->
    <movie-section :movies="movies" />
    <show-section :shows="shows" />
  </div>
  <div v-else>
    <trending-section :trending="trending" />
  </div>
</template>

<script>
/* import CardTemplate from "./CardTemplate.vue"; */
import MovieSection from "./MovieSection.vue";
import ShowSection from "./ShowSection.vue";
import TrendingSection from "./TrendingSection.vue";
export default {
  components: {
    TrendingSection,
    ShowSection,
    MovieSection,
  },
  props: {
    movies: Array,
    shows: Array,
    trending: Array,
  },
};
</script>

<style lang="scss" scoped></style>
