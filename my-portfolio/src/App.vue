<script setup>
import { ref } from 'vue'

const menuOpen = ref(false)

const closeMenu = () => {
  menuOpen.value = false
}
</script>

<template>
  <div>
    <!-- Sticky Navigation -->
    <header class="site-header">
      <nav>
        <a href="#top" class="nav-brand" @click="closeMenu">K</a>

        <button
          class="nav-toggle"
          @click="menuOpen = !menuOpen"
          aria-label="Toggle menu"
        >
          ☰
        </button>

        <ul :class="{ open: menuOpen }">
          <li><a href="#home" @click="closeMenu">Home</a></li>
          <li><a href="#about" @click="closeMenu">About Me</a></li>
          <li><a href="#skills" @click="closeMenu">Skills</a></li>
          <li><a href="#projects" @click="closeMenu">Projects</a></li>
          <li><a href="#certificates" @click="closeMenu">Certificates</a></li>
          <li><a href="#contact" @click="closeMenu">Contact</a></li>
        </ul>
      </nav>
    </header>

    <!-- Main Content Area -->
    <main id="top">
      <RouterView />
    </main>

    <!-- Footer -->
    <footer class="footer">
      <p>© 2026 Karah Fisher. Built with Vue.</p>
    </footer>
  </div>
</template>