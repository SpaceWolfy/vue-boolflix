<template>
  <header>
    <div class="title">BOOLFLIX</div>
    <input class="search-bar" type="text" />
  </header>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
header {
  display: flex;
  justify-content: space-between;
  padding: 30px 25px 15px 25px;
  background-color: black;

  .title {
    color: red;
    font-size: 28px;
  }

  .search-bar {
    height: 28px;
  }
}
</style>
