<template>
  <div class="container">
    <section class="movies_section">
      <div class="movie_card">
        <h2>Movies</h2>
        <ul>
          <li v-for="(movie, index) in moviesList" :key="index">
            <img :src=" 'https://image.tmdb.org/t/p/w342' + movie.poster_path"/>
            <div class="movie_description">
              <h4>Titolo:</h4>{{movie.title}}
              <h4>Titolo originale:</h4>{{movie.original_title}} 
              <h4>Voto:</h4>        
              <i v-for="n in 5" class="fa-star" :class="(n>=changeVote(movie.vote_average))?'fa-regular':'fa-solid'" :key="n"></i>
              <div class="overview">
                <h4>Overview:</h4>{{movie.overview}}
              </div>
            </div>
          </li>
       </ul>
      </div>
      
    </section>

    <section class="tv_section">
      <div class="movies_section">
        <div class="movie_card">
          <h2>Series</h2>
          <ul>
            <li v-for="(show, index) in tvShowsList" :key="index">
              <img class="poster" :src=" 'https://image.tmdb.org/t/p/w342' + show.poster_path"/>
                <div class="movie_description">
                  <h4>Titolo:</h4>{{show.name}}
                  <h4>Titolo originale:</h4>{{show.original_name}}
                  <h4>Voto:</h4>
                  <i v-for="n in 5" class="fa-star" :class="(n>=changeVote(show.vote_average))?'fa-regular':'fa-solid'" :key="n"></i>
                <div class="overview">
                  <h4>Overview:</h4>{{show.overview}}
                </div>
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
    height: 8000px;
    width: 100vw;
    background-color: rgb(57, 57, 57);

  }

   

  h2{
    color:white;
    text-align: center;
  }
  .little_flag{
    height: 20px;
    width: 20px;
  }

  .movie_card ul{
    display: flex;
    justify-content: center;
    flex-wrap:wrap;

    li{
      margin: 20px;
      height: 500px;
      width: calc(100% / 4);
      list-style: none;
      &:hover{
          cursor:pointer;
          transition: transform 0.8s;
          transform-style: preserve-3d;
          transform: rotateY(180deg);
          opacity: 30%;
        }

        
    }

    .movie_description{
      display:none;
      position: relative;
      bottom:500px;
      left: 10px;
      color:white;

      &:hover{
        display:block;
      }

        i {
          color: yellow;
        }
    }

    .overview {
      margin-right: 10px;
    }
  
  }
  
 




</style>