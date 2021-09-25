<template>
  <h1>{{ movie.Title }} </h1>
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