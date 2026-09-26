<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <nav class="navbar">
    <RouterLink to="/" class="logo">YourName.dev</RouterLink>
    <div class="links">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/projects">Projects</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  border-bottom: 1px solid #eee;
  position: sticky;
  top: 0;
  background: white;
  z-index: 10;
}
.logo {
  font-weight: bold;
  font-size: 1.2rem;
  text-decoration: none;
  color: #111;
}
.links a {
  margin-left: 1.5rem;
  text-decoration: none;
  color: #555;
}
.links a.router-link-active {
  color: #6366f1;
  font-weight: 600;
}
</style>
