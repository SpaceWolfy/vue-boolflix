<template>
  <div class="card-box">
    <img
      class="poster"
      :src="'https://image.tmdb.org/t/p/original/' + obj.poster_path"
      alt="Movie poster"
    />

    <div class="info">
      <div v-if="obj.val == 'movie'">
        <strong>Titolo: </strong>{{ obj.title }}
      </div>

      <div v-else><strong>Titolo: </strong>{{ obj.name }}</div>

      <div v-if="obj.val == 'movie'">
        <strong>Titolo originale: </strong>{{ obj.original_title }}
      </div>

      <div class="voto">
        <strong>Voto: </strong>

        <div v-for="(element, index) in voteArray" :key="index">
          <i v-if="index + 1 <= fromNumberToStar()" class="fas fa-star"></i>
          <i v-else class="far fa-star"></i>
        </div>
        <!-- {{ obj.vote_average }} -->
      </div>

      <div class="lingua">
        <strong>Lingua originale: </strong>

        <img
          v-if="languages.includes(obj.original_language)"
          class="flag"
          :src="require('@/assets/' + obj.original_language + '.png')"
          alt="Movie lang"
        />

        <div v-else>"{{ obj.original_language }}"</div>
      </div>

      <div><strong>Overview: </strong>{{ obj.overview }}</div>
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
    obj: Object,
  },
  methods: {
    fromNumberToStar: function () {
      if (this.obj.vote_average > 0 && this.obj.vote_average <= 10) {
        return Math.round(this.obj.vote_average / 2);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../style/CardTemplate.scss";
</style>
