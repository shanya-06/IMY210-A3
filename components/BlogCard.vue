<script setup>
defineProps({
  id: Number,
  title: String,
  content: String,
  author: String
});
</script>

<template>
  <article>
    <h2>{{ title }}</h2>
    <p>{{ content.substring(0, 100) }}...</p>
    <small>By {{ author }}</small>
<NuxtLink :to="`/blog/${id}`">Read more</NuxtLink>
  </article>
</template>
