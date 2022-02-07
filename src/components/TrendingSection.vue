<template>
  <div class="main">
    <div class="filter">Film del momento</div>

    <div class="card-container">
      <card-template
        v-for="trending in trendingFilm"
        :key="trending.id"
        :result="trending"
      />
    </div>

    <div class="filter">Serie del momento</div>

    <div class="card-container">
      <card-template
        v-for="trending in trendingSeries"
        :key="trending.id"
        :result="trending"
      />
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
    trendingFilm: Array,
    trendingSeries: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "../style/trendingsub.scss";
</style>
