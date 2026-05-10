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
      <article>
        <h1>{{ posts.data[0].Ttitle }}</h1>
        <p>{{ posts.data[0].content }}</p>
        <small>By {{ posts.data[0].author }}</small>
      </article>
    </div>
  </main>
</template>

<style scoped>
  article{
    background-color: rgba(154, 237, 211, 0.764);
    border-radius: 20px;
    padding-left: 40px;
    padding-right: 40px;
    padding-top: 1px;
    padding-bottom: 20px;
    text-align: center;
    margin: 15px;
    width: 70%;
    margin-left: auto;
    margin-right: auto;
    border: 2px solid rgb(0, 73, 73);
  }
  
  h2{
    text-align: center;
  }

  hr{
    border: 2px solid rgba(7, 84, 84, 0.874);
    border-radius: 10px;
  }

  p{
    width: 60%;
    text-align: center;
    background-color: rgba(150, 220, 197, 0.627);
    border-radius: 10px;
    padding: 10px;
    margin-left: auto;
    margin-right: auto;
  }

  a{
    text-decoration: none;
    text-align: center;
    color: rgb(16, 95, 95);
  }

  *{
    color: rgb(0, 41, 41);
  }

  article:hover{
    background-color: rgb(237, 255, 255);
    p{
      background-color: rgba(176, 235, 215, 0.486);
    };
  }

  a:hover{
    color: rgb(1, 34, 35);
    font-size: large;
    background-color: rgb(176, 213, 236);
    border-radius: 10px;
    padding: 7px;
  }
</style>