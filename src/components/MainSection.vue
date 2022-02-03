<template>
  <div class="main">
    <card-template
      v-for="movie in moviesFilter"
      :key="movie.id"
      :movie="movie"
    />
  </div>
</template>

<script>
import CardTemplate from "./CardTemplate.vue";
export default {
  components: { CardTemplate },
  props: {
    moviesFilter: Array,
  },
};
</script>

<style lang="scss" scoped>
.main {
  display: flex;
  flex-wrap: wrap;
  padding: 20px;
}
</style>
