<template>
  <nav style="padding: 1rem; background: #f5f5f5; border-bottom: 1px solid #ddd;">
    <ul style="display: flex; gap: 1rem; list-style: none; margin: 0; padding: 0;">
      <li><NuxtLink to="/" active-class="active-link">Home</NuxtLink></li>
      <li><NuxtLink to="/search" active-class="active-link">Search</NuxtLink></li>
      <!-- Example blog link -->
      <li><NuxtLink to="/blog/2" active-class="active-link">Blog Example</NuxtLink></li>
    </ul>
  </nav>
</template>

<style scoped>
/* Style for active link */
.active-link {
  font-weight: bold;
  color: #0070f3; /* Nuxt blue */
  text-decoration: underline;
}
</style>
