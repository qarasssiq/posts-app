<template>
  <div>
    <article>
      <h1 class="text-2xl font-bold">{{ post.title }}</h1>
      <p class="text-gray-300">{{ user.name }}</p>
      <p>{{ post.body }}</p>
    </article>
  </div>
</template>

<script setup>
const { id } = useRoute().params;

const { data: post } = await useFetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
const { data: user } = await useFetch(`https://jsonplaceholder.typicode.com/users/${post.value.userId}`);
</script>

<style lang="sass" scoped>
</style>