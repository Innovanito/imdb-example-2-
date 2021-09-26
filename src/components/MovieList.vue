<template>
  <div class="container">
    <div 
      :class="{ 'no-result': !movie.length }"
      class="inner">
      <div 
        v-if="message"
        class="message">
        {{ message}}
      </div>
      <div 
        v-else
        class="movies">
        <MovieItem 
        v-for="movie in movies"
        :key="movie.imdbID"
        :movie="movie"/>
      </div>
    </div>
  </div>
</template>

<script>
import MovieItem from './MovieItem.vue'

export default {
  components: {
    MovieItem
  },
  computed: {
    movies() {
      return this.$store.state.movie.movies
    },
    message() {
      return this.$store.state.movie.message
    }
  }
}
</script>

<style lang="scss" scoped>
@import "~/scss/main";

.container {
  margin-top: 30px;
  .inner {
    background-color: $gray-200;
    padding: 10px 0;
    border-radius: 4px;
    text-align: center;
  }
  .movies {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style>