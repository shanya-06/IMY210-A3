<template>
  <!--Shanya Nair - u25061845-->
  <nav>
    <ul>
      <li><NuxtLink to="/" active-class="active-link">Home</NuxtLink></li>
      <li><NuxtLink to="/search" active-class="active-link">Search</NuxtLink></li>
     
    </ul>
  </nav>
</template>

<style scoped>
nav{
  padding: 20px;
  font-size: large;
  text-align: center;
  background-color: rgb(168, 219, 216);
}

ul{
  display: inline-flex;
  margin: 10px;
  
}

li{
  margin: 20px;
  margin-left: 40px;
  margin-right: 40px;
  list-style: none;
  text-align: center;
}

.active-link {
  font-weight: bold;
  color: #00d0ff; 
  border: 2px solid #015860c7;
  border-radius: 7px;
  padding: 4px;
  background-color: #038591b1;
}

a:hover{
  color: white;
}

a{
  text-decoration: none;
  color: #015860;
}
</style>
