<template>
  <header>
    <div class="title">BOOLFLIX</div>
    <div class="search-cont">
      <input v-model="movieKeyWord" class="search-bar" type="text" />
      <button class="search" @click="$emit('search', movieKeyWord)">
        Search
      </button>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      movieKeyWord: "",
    };
  },
};
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
  .search-cont {
    height: 28px;

    .search-bar {
      height: 100%;
      margin-right: 10px;
    }

    button {
      height: 100%;
    }
  }
}
</style>
