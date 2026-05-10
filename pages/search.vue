<script setup>
//Shanya Nair - u25061845
import { ref } from "vue";
import BlogCard from "~/components/BlogCard.vue";
import SearchBar from "~/components/SearchBar.vue";

const query = ref("");
const results = ref([]);
const error = ref(null);

async function search() {
  try {
    if (!query.value) {
      results.value = [];
      return;
    }

    const res = await fetch(
      `https://phenomenal-respect-ee4f828725.strapiapp.com/api/blogs?filters[$or][0][title][$containsi]=${encodeURIComponent(query.value)}&filters[$or][1][author][name][$containsi]=${encodeURIComponent(query.value)}&populate=author`
    );

    const data = await res.json();
    console.log(data);
    results.value = data.data;
    error.value = null;
  } catch (err) {
    error.value = "Failed to fetch search results.";
  }
}
</script>

<template>
  <main style="padding: 2rem;">
    <h1> Search Blogs</h1>

    <div id="search">
      <SearchBar v-model="query" @search="search" />
    </div>

    <div v-if="error">{{ error }}</div>
    <div v-else-if="results.length === 0 && query">No results found.</div>

    <div v-else>
      <BlogCard
        v-for="blog in results"
        :key="blog.id"
        :blog="blog.attributes"
      />
    </div>
  </main>
</template>

<style scoped>
 h1{
  text-align: center;
 }

 #search{
  text-align: center;
 }
</style>
