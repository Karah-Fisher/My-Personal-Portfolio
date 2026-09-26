<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="app-shell">
    <header>
      <nav>
        <RouterLink to="/" class="nav-brand">K</RouterLink>
        <ul>
          <li><RouterLink to="/">Home</RouterLink></li>
          <li><RouterLink to="/about">About Me</RouterLink></li>
          <li><RouterLink to="/projects">Projects</RouterLink></li>
          <li><RouterLink to="/contact">Contact</RouterLink></li>
        </ul>
      </nav>
    </header>

    <RouterView />

    <footer class="footer">
      <p>© 2026 Karah. Built with Vue.</p>
    </footer>
  </div>
</template>
