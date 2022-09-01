<template>
  <div>
    <ul>
      
      <li v-for="(movie, index) in moviesList" :key="index">
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
  moviesList: Array
}
}
</script>

<style scoped lang="scss">

</style>