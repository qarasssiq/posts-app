<template>
  <div class="card text-center">
    <NuxtLink :to="`/posts/${post.id}`">
      <h3 class="text-lg font-bold text-blue-500 m-2 text-left capitalize">{{ post.title }}</h3>
    </NuxtLink>
    <p class="text-left m-2 capitalize">{{ post.body }}</p>
    <p class="text-left m-2 capitalize text-gray-400">{{ user.name }}</p>
  </div>
</template>

<script>
  export default {
  props: {
    post: Object,
    user: Object
  }
}
</script>

<style scoped>
  .thumb {
    max-height: 120px;
    max-width: 70%;
    margin: 0 auto;
  }
</style>