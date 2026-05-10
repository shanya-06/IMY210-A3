<script setup>
import BlogCard from "~/components/BlogCard.vue";

// Fetch all blogs from Strapi
const { data: posts, error } = await useFetch(
  "https://phenomenal-respect-ee4f828725.strapiapp.com/api/blogs"
);
</script>

<template>
  <main style="padding: 2rem;">
    <h1>📰 Homepage</h1>

    <div v-if="error">
      <p>Error loading posts.</p>
    </div>

    <div v-else-if="!posts || posts.data.length === 0">
      <p>No posts found.</p>
    </div>

    <div v-else>
    <BlogCard
  v-for="post in posts.data"
  :key="post.documentId"
  :id="post.documentId"
  :title="post.Ttitle"
  :content="post.content"
  :author="post.author"
/>


    </div>
  </main>
</template>
