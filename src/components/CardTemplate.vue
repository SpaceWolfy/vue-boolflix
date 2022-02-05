<template>
  <div class="card-box">
    <img
      v-if="result.poster_path"
      class="poster"
      :src="'https://image.tmdb.org/t/p/original/' + result.poster_path"
      alt="result poster"
    />

    <div v-else class="not-found">
      <img
        src="https://media.istockphoto.com/vectors/error-page-or-file-not-found-icon-vector-id924949200?k=20&m=924949200&s=170667a&w=0&h=-g01ME1udkojlHCZeoa1UnMkWZZppdIFHEKk6wMvxrs="
        alt=""
      />
    </div>

    <div class="info">
      <div v-if="result.title">
        <div><strong>Titolo: </strong>{{ result.title }}</div>

        <div>
          <strong>Titolo originale: </strong>{{ result.original_title }}
        </div>
      </div>

      <div v-else>
        <div><strong>Titolo: </strong>{{ result.name }}</div>

        <div><strong>Titolo originale: </strong>{{ result.original_name }}</div>
      </div>

      <div class="voto">
        <strong>Voto: </strong>

        <div v-for="(element, index) in voteArray" :key="index">
          <i v-if="index + 1 <= fromNumberToStar()" class="fas fa-star"></i>
          <i v-else class="far fa-star"></i>
        </div>
        <!-- {{ result.vote_average }} -->
      </div>

      <div class="lingua">
        <strong>Lingua originale: </strong>

        <img
          v-if="languages.includes(result.original_language)"
          class="flag"
          :src="require('@/assets/' + result.original_language + '.png')"
          alt="result lang"
        />

        <div v-else>"{{ result.original_language }}"</div>
      </div>

      <div><strong>Overview: </strong>{{ result.overview }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      languages: ["it", "en", "de", "us", "fr"],
      voteArray: [1, 2, 3, 4, 5],
    };
  },
  props: {
    result: Object,
  },
  methods: {
    fromNumberToStar: function () {
      if (this.result.vote_average > 0 && this.result.vote_average <= 10) {
        return Math.round(this.result.vote_average / 2);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../style/CardTemplate.scss";
</style>
