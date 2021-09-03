<template>
  <div class="flex flex-wrap flex-grow">
    <MovieCard v-for="movie in movies" :key="movie.imdbID" :movie="movie" />
  </div>
</template>
<script>
import MovieCard from "../components/MovieCard.vue";
export default{
  components:{MovieCard},
  async asyncData(){
    const res = await fetch(`http://www.omdbapi.com/?s=batman&apikey=1743cb13&type=movie`)
    const data = await res.json()
    return {
      movies: data.Search,
    }
  }
}

</script>
