<template>
  <div>
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
  </div>
</template>

<script>
export default {
name: 'MyMain',
props: {
  moviesList: Array
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