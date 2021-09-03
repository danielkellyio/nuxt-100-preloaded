<template>
  <div v-if="movie" class="flex gap-3">
    <img
      :src="movie.Poster"
    />
    <div>
      <h1 class="text-3xl">{{movie.Title}}</h1>
      <p>
        <span class="pill">{{movie.Rated}}</span>
        <span class="pill">{{movie.Year}}</span>
        <span class="pill">⭐️{{movie.Ratings[0].Value}}</span>
        <span class="pill">{{movie.Runtime}}</span>
      </p>
      <h2 class="mt-5 opacity-50">Plot</h2>
      <p>{{movie.Plot}}</p>
      <h2 class="mt-5 opacity-50">Actors</h2>
      <p>{{movie.Actors}}</p>
      <h2 class="mt-5 opacity-50">Genre</h2>
      <p>{{movie.Genre}}</p>
      <div class="mt-10"> 
        <a class="bg-blue p-3 rounded" :href="`https://www.imdb.com/title/${movie.imdbID}/`">View on IMDB</a>
      </div>
    </div>
  </div>
</template>
<script>
export default{
  async asyncData({route}){
    const res = await fetch(`http://www.omdbapi.com/?i=${route.params.id}&apikey=1743cb13&plot=full`)
    const movie = await res.json()
    return {movie}
  }
}
</script>
<style>
  .bg-blue{
    background:#4996c5;
  }
  .pill{
    padding:2px 4px;
    background:#4996c5;
    border-radius: 4px;
    font-size:.7rem;
    color:white;
  }
</style>