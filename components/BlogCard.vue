<script setup>
//Shanya Nair - u25061845
defineProps({
  id: String,
  title: String,
  content: String,
  author: String
});
</script>

<template>
  <article>
    <h2>{{ title }}</h2><hr>
    <small>Author: {{ author }}</small>
    <p>{{ content.substring(0, 100) }}...</p>
    
<NuxtLink :to="`/blog/${id}`">Read more</NuxtLink>
  </article>
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
  }

  article:hover p{
      background-color: rgba(176, 235, 215, 0.486);
    };

  a:hover{
    color: rgb(1, 34, 35);
    font-size: large;
    background-color: rgb(176, 213, 236);
    border-radius: 10px;
    padding: 7px;
  }
</style>
