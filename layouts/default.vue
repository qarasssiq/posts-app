<template>
  <div>
    <header class="shadow-sm bg-white">
      <nav class="container mx-auto py-4 px-8 flex justify-between">
        <NuxtLink to="/" class="font-bold text-xl">posts-app</NuxtLink>
        <ul class="flex gap-4">
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li><NuxtLink to="/posts">Posts</NuxtLink></li>
        </ul>
      </nav>
    </header>
    <div class="container mx-auto py-4 px-8">
      <slot />
    </div>
  </div>
</template>

<script>
</script>

<style scoped>
.router-link-exact-active {
  color: #12b488;
}
</style>