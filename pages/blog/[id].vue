<script setup>
const route = useRoute();

const { data: posts, error } = await useFetch(
  `https://phenomenal-respect-ee4f828725.strapiapp.com/api/blogs?filters[documentId][$eq]=${route.params.id}`
);
</script>

<template>
  <main style="padding: 2rem;">
    <div v-if="error">Error loading post.</div>
    <div v-else-if="!posts || posts.data.length === 0">
      <p>Post not found.</p>
      <NuxtLink to="/">Back to Homepage</NuxtLink>
    </div>
    <div v-else>
      <h1>{{ posts.data[0].Ttitle }}</h1>
      <p>{{ posts.data[0].content }}</p>
      <small>By {{ posts.data[0].author }}</small>
    </div>
  </main>
</template>
