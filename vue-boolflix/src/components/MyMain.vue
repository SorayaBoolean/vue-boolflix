<template>
  <div>
    <ul>
      <li>
        titolo - titolo originale- lingua - voto
      </li>
      <li v-for="(movie, index) in movieList" :key="index">
        {{movie.title}}
        {{movie.original_title}}
        {{movie.original_language}}
        {{movie.average}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
name: 'MyMain',
props: {
  movieList: Array
}
}
</script>

<style scoped lang="scss">

</style>