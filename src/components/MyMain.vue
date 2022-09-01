<template>
  <div>
    <section class="movies_section">
      <h2>Movies List:</h2>
      <ul>
      <li v-for="(movie, index) in moviesList" :key="index">
        <img :src=" 'https://image.tmdb.org/t/p/w342' + movie.poster_path"/>
        {{movie.title}}
        {{movie.original_title}}
        <img class="little_flag" v-if="usedFlags.includes(movie.original_language)" 
        :src="require('@/assets/img/' + movie.original_language +'.png')"/>
        <span v-else>{{movie.original_language}}</span>
        <div>
          <i v-for="n in 5" class="fa-star" :class="(n>=changeVote(movie.vote_average))?'fa-regular':'fa-solid'" :key="n"></i>
        </div>
      </li>
    </ul>
    </section>

    <section class="tv_section">
      <h2>Tv Shows List:</h2>
      <ul>
      <li v-for="(show, index) in tvShowsList" :key="index">
        <img :src=" 'https://image.tmdb.org/t/p/w342' + show.poster_path"/>
        {{show.name}}
        {{show.original_name}}
        <img class="little_flag" v-if="usedFlags.includes(show.original_language)" 
        :src="require('@/assets/img/' + show.original_language +'.png')"/>
        <span v-else>{{show.original_language}}</span>
        <div>
          <i v-for="n in 5" class="fa-star" :class="(n>=changeVote(show.vote_average))?'fa-regular':'fa-solid'" :key="n"></i>
        </div>
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
},
methods: {
  changeVote (vote) {
    return Math.ceil(vote / 2)
  }
}
}
</script>

<style scoped lang="scss">
.little_flag{
  height: 10px;
  width:20px;
}
</style>