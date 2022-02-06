<template>
  <div class="header-container">
    <div class="gradient">
      <header>
        <img class="logo" src="../assets/Logonetflix.png" alt="" />
        <div class="search-cont">
          <input v-model="movieKeyWord" class="search-bar" type="text" />
          <button class="search" @click="$emit('search', movieKeyWord)">
            Search
          </button>
        </div>
      </header>

      <div class="jumbotron-info"></div>
    </div>
  </div>
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
.header-container {
  background-image: url("../assets/stranger4.jpg");
  height: 650px;
  background-position-y: -400px;
  background-repeat: no-repeat;

  .gradient {
    height: 100%;
    background: linear-gradient(to bottom, transparent 30%, #0c0c0c 99%);
  }

  header {
    display: flex;
    justify-content: space-between;
    padding: 30px 25px 15px 25px;

    .logo {
      width: 100px;
      margin-left: 30px;
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
}
</style>
