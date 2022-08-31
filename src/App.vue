<template>
  <div id="app">
    <MyHeader @search="searching"/>
    <MyMain :moviesList="moviesList"/>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    MyMain,
    MyHeader,
},
data() {
  return {
    urlAPI:'https://api.themoviedb.org/3',
    apiKEY: 'e601b9a31a23f60982ea7c2f7e96a2b7',
    language:'it-IT',
    moviesList: []
  }
},
methods: {
  searching (searchedText) {
    axios.get(this.urlAPI + '/search/movie?api=key=' + this.apiKEY + '&language=' + this.language + '&query=' + searchedText)
    .then( response => {
      this.moviesList = response.data.results;
    })
    .catch(err => {
      console.log(err)
    })
  }
}
 
}
</script>

<style lang="scss">

</style>
