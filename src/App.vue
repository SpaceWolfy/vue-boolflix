<template>
  <div id="app">
    <header-main />
    <main-section />
  </div>
</template>

<script>
import HeaderMain from "./components/HeaderMain.vue";
import MainSection from "./components/MainSection.vue";

export default {
  name: "App",
  components: {
    HeaderMain,
    MainSection,
  },
};
</script>

<style lang="scss">
@import "style/main.scss";
</style>
