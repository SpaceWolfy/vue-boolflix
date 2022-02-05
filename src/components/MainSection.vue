<template>
  <div class="main" v-if="movies.length !== 0 || shows.length !== 0">
    <!-- <card-template v-for="obj in movies" :key="obj.id" :obj="obj" /> -->
    <movie-section :movies="movies" />
    <show-section :shows="shows" />
  </div>
</template>

<script>
/* import CardTemplate from "./CardTemplate.vue"; */
import MovieSection from "./MovieSection.vue";
import ShowSection from "./ShowSection.vue";
export default {
  components: {
    /* CardTemplate */
    ShowSection,
    MovieSection,
  },
  props: {
    movies: Array,
    shows: Array,
  },
};
</script>

<style lang="scss" scoped></style>
