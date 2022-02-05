<template>
  <div class="main">
    <div class="filter">Trending</div>

    <div class="card-container">
      <card-template
        v-for="trending in trending"
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
    trending: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "../style/subsection.scss";
</style>
