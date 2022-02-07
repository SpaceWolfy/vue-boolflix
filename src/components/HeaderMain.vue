<template>
  <div class="header-container">
    <div class="gradient">
      <header>
        <div class="left-cont">
          <img class="logo" src="../assets/Logonetflix.png" alt="" />

          <ul>
            <li>Home</li>
            <li>Serie TV</li>
            <li>Film</li>
            <li>Aggiunti di recente</li>
            <li>La mia lista</li>
          </ul>
        </div>

        <div class="right-cont">
          <div class="search-cont">
            <input v-model="movieKeyWord" class="search-bar" type="text" />
            <button class="search" @click="$emit('search', movieKeyWord)">
              <i class="fas fa-search"></i>
            </button>
          </div>

          <div class="notifications"><i class="fas fa-bell"></i></div>

          <div class="propic">
            <img
              src="https://mir-s3-cdn-cf.behance.net/project_modules/disp/84c20033850498.56ba69ac290ea.png"
              alt=""
            />
            <i class="fas fa-caret-down"></i>
          </div>
        </div>
      </header>

      <div class="jumbotron-info">
        <div class="jumbo-container">
          <img src="../assets/stranger4logo.png" alt="" />

          <div class="jumbo-btns">
            <button class="j-btn"><i class="fas fa-play"></i> Riproduci</button>
            <button class="j-btn">
              <i class="fas fa-plus"></i> La mia lista
            </button>
          </div>

          <div class="trama">
            <h2>Prossimamente su Netflix</h2>
            Un seguito diretto degli eventi della terza stagione, prossimamente
            su Netflix!
          </div>
        </div>
      </div>
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
@import "../style/headermain.scss";
</style>
