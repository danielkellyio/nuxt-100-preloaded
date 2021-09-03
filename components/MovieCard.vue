<template>
  <div
    class="
      m-2
      shadow-md
      w-1/3
      flex-grow
      rounded
      overflow-hidden
    "
    style="border: 1px solid #eee"
  >
  <nuxt-link :to="`/movies/${movie.imdbID}`" class="flex items-center gap-2">
      <img
        :src="movie.Poster"
        width="100"
      />
      <span>
        {{movie.Title}}
      </span>
    </nuxt-link>
  </div>
</template>
<script>
export default{
  props:{
    movie: {type: Object, required: true},
  },
}
</script>
