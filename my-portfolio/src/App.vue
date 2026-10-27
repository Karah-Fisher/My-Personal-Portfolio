<script setup>
import { ref, onMounted } from 'vue'

const menuOpen = ref(false)
const activeSection = ref('home')

const closeMenu = () => {
  menuOpen.value = false
}

onMounted(() => {
  // Find all the sections with an ID
  const sections = document.querySelectorAll('section[id]')

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          activeSection.value = entry.target.id
        }
      })
    },
    { rootMargin: '-20% 0px -60% 0px' }, // Triggers when section is in the middle of the screen
  )

  sections.forEach((section) => observer.observe(section))
})
</script>

<template>
  <div>
    <!-- Sticky Navigation -->
    <header class="site-header">
      <nav>
        <a href="#top" class="nav-brand" @click="closeMenu">K</a>

        <button class="nav-toggle" @click="menuOpen = !menuOpen" aria-label="Toggle menu">
          ☰
        </button>

        <ul :class="{ open: menuOpen }">
          <li><a href="#home" @click="closeMenu">Home</a></li>
          <li>
            <a href="#about" :class="{ active: activeSection === 'about' }" @click="closeMenu"
              >About Me</a
            >
          </li>
          <li>
            <a href="#skills" :class="{ active: activeSection === 'skills' }" @click="closeMenu"
              >Skills</a
            >
          </li>
          <li>
            <a href="#projects" :class="{ active: activeSection === 'projects' }" @click="closeMenu"
              >Projects</a
            >
          </li>
          <li>
            <a
              href="#certificates"
              :class="{ active: activeSection === 'certificates' }"
              @click="closeMenu"
              >Certificates</a
            >
          </li>
          <li>
            <a href="#contact" :class="{ active: activeSection === 'contact' }" @click="closeMenu"
              >Contact</a
            >
          </li>
        </ul>
      </nav>
    </header>

    <!-- Main Content Area -->
    <main id="top">
      <RouterView />
    </main>

    <!-- Footer -->
    <footer class="footer">
      <div class="footer-content">
        <div class="footer-logo">KF</div>
        <p>© 2026 Karah Fisher. Built with Vue.</p>
      </div>
    </footer>
  </div>
</template>
