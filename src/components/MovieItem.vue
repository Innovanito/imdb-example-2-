<template>
  <h1>{{ movie.imdbID }} </h1>
</template>

<script>
export default {
  props: {
    movie: {
      type: Object,
      default: () => ({})
    }
  }
}
</script>