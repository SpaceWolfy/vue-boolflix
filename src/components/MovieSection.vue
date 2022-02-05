<template>
  <div class="main">
    <div class="filter">Film filtrati per ricerca:</div>

    <div class="card-container">
      <card-template v-for="movie in movies" :key="movie.id" :result="movie" />
    </div>
  </div>
</template>

<script>
import CardTemplate from "./CardTemplate.vue";
export default {
  components: {
    CardTemplate,
  },
  props: {
    movies: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "../style/subsection.scss";
</style>
