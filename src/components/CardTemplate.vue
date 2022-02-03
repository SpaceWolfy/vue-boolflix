<template>
  <div class="card-box">
    <img
      :src="'https://image.tmdb.org/t/p/original/' + movie.poster_path"
      alt="Movie poster"
    />

    <div class="info">
      <div><strong>Titlo: </strong>{{ movie.title }}</div>

      <div><strong>Titlo originale: </strong>{{ movie.original_title }}</div>

      <div><strong>Voto: </strong>{{ movie.vote_average }}</div>

      <div>
        <strong>Lingua originale: </strong>"{{ movie.original_language }}"
      </div>

      <div><strong>Overview: </strong>{{ movie.overview }}</div>
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
  height: 350px;
  margin: 20px;
  width: calc((100% / 7) - 40px);
  border: 2px solid white;
  cursor: pointer;

  img {
    height: 100%;
    width: 100%;
  }

  .info {
    padding: 10px;
    display: none;
    color: white;
  }

  &:hover {
    background-color: black;
    overflow: auto;

    img {
      display: none;
    }

    .info {
      display: block;

      div {
        padding: 3px;

        & strong {
          color: white;
        }

        &:nth-child(3) {
          color: yellow;
        }
      }
    }
  }
}
</style>
