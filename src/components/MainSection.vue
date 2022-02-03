<template>
  <div class="main">
    <card-template v-for="obj in filterAll" :key="obj.id" :obj="obj" />
  </div>
</template>

<script>
import CardTemplate from "./CardTemplate.vue";
export default {
  components: { CardTemplate },
  props: {
    filterAll: Array,
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
