<script setup>
import BlogCard from "~/components/BlogCard.vue";

// Shanya Nair - u25061845
const { data: posts, error } = await useFetch(
  "https://phenomenal-respect-ee4f828725.strapiapp.com/api/blogs"
);
</script>

<template>
  <main>
    <h1> Homepage</h1>

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

<style scoped>
  main{
    padding: 2rem;
  }

  h1{
    text-align: center;
  }
</style>
