<template>
  <div class="flex items-center justify-center p-4 pt-0">
    <div class="flex border-2 rounded">
      <input
        type="text"
        class="px-4 py-2 w-full sm:w-80"
        v-model="authorSearch"
        placeholder="Filter by author..."
      />
      <div class="flex items-center justify-center px-4 border-l">
        <svg
          class="w-6 h-6 text-gray-600"
          fill="currentColor"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
        >
          <path
            d="M16.32 14.9l5.39 5.4a1 1 0 0 1-1.42 1.4l-5.38-5.38a8 8 0 1 1 1.41-1.41zM10 16a6 6 0 1 0 0-12 6 6 0 0 0 0 12z"
          />
        </svg>
      </div>
    </div>
  </div>
  <div class="grid sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-5">
    <div v-for="post in filteredPosts">
      <PostCard
        :post="post"
        :user="users.find((user) => user.id == post.userId)"
      />
    </div>
  </div>
</template>

<script setup>
const authorSearch = ref("");

const { data: posts } = await useFetch(
  "https://jsonplaceholder.typicode.com/posts"
);
const { data: users } = await useFetch(
  "https://jsonplaceholder.typicode.com/users"
);

const filteredPosts = computed(() => {
  return posts.value.filter((post) => {
    const user = users.value.find((user) => user.id === post.userId);
    return (
      user && user.name.toLowerCase().includes(authorSearch.value.toLowerCase())
    );
  });
});
</script>

<style lang="sass" scoped>
</style>