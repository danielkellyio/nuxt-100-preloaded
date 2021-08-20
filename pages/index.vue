<template>
  <div class="flex flex-wrap flex-grow">
    <PostCard v-for="post in posts" :key="post.id" :post="post" />
  </div>
</template>
<script>
import PostCard from "../components/PostCard.vue";
export default{
  components:{PostCard},
  async asyncData(){
    const res = await fetch(`https://jsonplaceholder.typicode.com/posts`)
    const posts = await res.json()
    return {posts}
  }
}

</script>
