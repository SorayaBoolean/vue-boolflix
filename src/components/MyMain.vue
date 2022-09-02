<template>
  <div class="container">
    <section class="movies_section">
      <div class="movie_card">
        <ul>
          <li v-for="(movie, index) in moviesList" :key="index">
            <img :src=" 'https://image.tmdb.org/t/p/w342' + movie.poster_path"/>
            <div class="movie_description">
              <h4>Titolo:</h4>{{movie.title}}
              <h4>Titolo originale:</h4>{{movie.original_title}} 
              <h4>Voto:</h4>        
              <i v-for="n in 5" class="fa-star" :class="(n>=changeVote(movie.vote_average))?'fa-regular':'fa-solid'" :key="n"></i>
          </div>
          </li>
       </ul>
      </div>
      
    </section>

    <section class="tv_section">
      <div class="movies_section">
        <div class="movie_card">
          <ul>
          <li v-for="(show, index) in tvShowsList" :key="index">
            <img :src=" 'https://image.tmdb.org/t/p/w342' + show.poster_path"/>
            <div class="movie_description">
              <h4>Titolo:</h4>{{show.name}}
              <h4>Titolo originale:</h4>{{show.original_name}}
              <h4>Voto:</h4>
              <i v-for="n in 5" class="fa-star" :class="(n>=changeVote(show.vote_average))?'fa-regular':'fa-solid'" :key="n"></i>
            </div>
          </li>
    </ul>

        </div>
      </div>
      
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
}}

</script>

<style scoped lang="scss">
  .container{
    height: 100%;
    width: 100vw;
    background-color: rgb(57, 57, 57);
  }
  .little_flag{
    height: 20px;
    width: 20px;
  }
  .movies_section{
    display:flex;
  }
  .movie_card{
    ul li {
      list-style: none;
    }
    .poster{
      width:200px;
      height:100%;
    }
  }
  .movie_card ul{
    display: flex;
    flex-wrap:wrap;
    margin: auto;

    li{
      margin: 10px;
      width: calc(100% / 4);
      border:1px solid violet;

    }
  
  }
  
 




</style>