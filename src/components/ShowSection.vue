<template>
  <div class="main">
    <div class="filter">Serie filtrate per ricerca:</div>
    <div class="card-container">
      <card-template v-for="show in shows" :key="show.id" :result="show" />
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
    shows: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "../style/subsection.scss";
</style>
