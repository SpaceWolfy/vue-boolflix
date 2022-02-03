<template>
  <div class="card-box">
    <img
      src="https://ssl-static.libsyn.com/p/assets/0/3/f/4/03f4dc2f16cc5d19/Back_to_the_Future.jpg"
      alt="Movie poster"
    />

    <div class="info">
      <div>{{ movie.title }}</div>
      <div>ciao</div>
      <div>ciao</div>
      <div>ciao</div>
      <div>ciao</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    movie: Object,
  },
};
</script>

<style lang="scss" scoped>
.card-box {
  margin: 20px;
  height: 350px;
  width: 240px;
  border: 2px solid white;
  cursor: pointer;

  img {
    height: 100%;
    width: 100%;
  }

  .info {
    display: none;
    color: white;
  }

  &:hover {
    background-color: black;

    img {
      display: none;
    }

    .info {
      display: block;
    }
  }
}
</style>
