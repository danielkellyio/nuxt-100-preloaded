<template>
  <div v-if="post">
    <h1 class="text-3xl">{{ post.title }}</h1>
    <div>{{ post.body }}</div>
  </div>
</template>
<script>
export default{
  async asyncData({route}){
    const res = await fetch(
      `https://jsonplaceholder.typicode.com/posts/${route.params.id}`
    )
    const post = await res.json()
    return {post}
  }
}
</script>
