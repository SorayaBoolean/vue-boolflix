<template>
  <div>
    <section class="movies_section">
      <h2>Movies List:</h2>
      <ul>
      <li v-for="(movie, index) in moviesList" :key="index">
        {{movie.title}}
        {{movie.original_title}}
        <img v-if="usedFlags.includes(movie.original_language)" 
        :src="require('@/assets/img/' + movie.original_language +'.png')"/>
        <span v-else>{{movie.original_language}}</span>
        {{movie.vote_average}}
      </li>
    </ul>
    </section>
    <section class="tv_section">
      <h2>Tv Shows List:</h2>
      <ul>
      <li v-for="(show, index) in tvShowsList" :key="index">
        {{show.name}}
        {{show.original_name}}
        <img v-if="usedFlags.includes(show.original_language)" 
        :src="require('@/assets/img/' + show.original_language +'.png')"/>
        <span v-else>{{show.original_language}}</span>
        {{show.vote_average}}
      </li>
    </ul>
    </section>
    
  </div>
</template>

<script>
export default {
name: 'MyMain',
props: {
  moviesList: Array,
  tvShowsList: Array
},
data(){
  return {
    usedFlags: ['en','it', 'fr']
  }
}
}
</script>

<style scoped lang="scss">
img{
  height: 10px;
  width:20px;
}
</style>