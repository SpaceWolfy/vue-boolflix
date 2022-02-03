<template>
  <div class="card-box">
    <img
      src="https://ssl-static.libsyn.com/p/assets/0/3/f/4/03f4dc2f16cc5d19/Back_to_the_Future.jpg"
      alt="Movie poster"
    />

    <div class="info">
      <div>ciao</div>
      <div>ciao</div>
      <div>ciao</div>
      <div>ciao</div>
      <div>ciao</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return { isHovering: false };
  },
};
</script>

<style lang="scss" scoped>
.card-box {
  height: 350px;
  width: 240px;

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
