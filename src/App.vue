<template>
  <div id="app">
    <NavBar></NavBar>
    <div class="row justify-content-center">
      <div class="row row-cols-1 row-cols-md-3 g-4">
          <GridCard v-for="movie in movies" :key=movie.id :obj=movie></GridCard>
      </div>
    </div>

  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import GridCard from './components/GridCard.vue'


import axios from 'axios'

export default {
  name: 'App',
  components: {
    NavBar,
    GridCard
  },
  mounted(){
    var link = "https://api.themoviedb.org/3/movie/now_playing?api_key=ab1f4dbc082f96d0289af4a0c5cf5a52&language=en-US&page=1"
    axios.get(link)
    .then((res)=>{
        console.log("API Response",res);
        this.movies = res.data.results;
        console.log("Object Array",this.movies);
    })
    .catch(error=>{console.log(error);})
  },
  data(){
    return{
      movies: [],

    }
  },
  methods:{
  
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
