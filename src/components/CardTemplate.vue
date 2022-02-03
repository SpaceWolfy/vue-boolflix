<template>
  <div class="card-box">
    <img
      class="poster"
      :src="'https://image.tmdb.org/t/p/original/' + movie.poster_path"
      alt="Movie poster"
    />

    <div class="info">
      <div><strong>Titlo: </strong>{{ movie.title }}</div>

      <div><strong>Titlo originale: </strong>{{ movie.original_title }}</div>

      <div><strong>Voto: </strong>{{ movie.vote_average }}</div>

      <div>
        <strong>Lingua originale: </strong>

        <img
          v-if="languages.includes(movie.original_language)"
          class="flag"
          :src="require('@/assets/' + movie.original_language + '.png')"
          alt="Movie lang"
        />

        <div v-else>"{{ movie.original_language }}"</div>
      </div>

      <div><strong>Overview: </strong>{{ movie.overview }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return { languages: ["it", "en", "de", "us", "fr"] };
  },
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

  .poster {
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

    .poster {
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

        .flag {
          width: 25px;
          height: 15px;
        }
      }
    }
  }
}
</style>
