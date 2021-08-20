<template>
  <div
    class="
      flex
      m-2
      gap-2
      items-center
      shadow-md
      w-1/4
      flex-grow
      rounded
      overflow-hidden
    "
    style="border: 1px solid #eee"
  >
    <img
      src="https://via.placeholder.com/150"
      style="background: #cccccc"
      width="150"
      height="150"
    />
    <nuxt-link :to="`/posts/${post.id}`">
      {{ post.title }}
    </nuxt-link>
  </div>
</template>
<script>
export default{
  props:{
    post: {type: Object, required: true},
  }
}
</script>
