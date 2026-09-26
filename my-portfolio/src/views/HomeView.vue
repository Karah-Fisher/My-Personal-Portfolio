<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <main>
    <section class="hero-container">
      <div class="hero-content">
        <h1>Hey!, I'm <span class="highlight">Karah</span></h1>
        <br />
        <h2>Aspiring Full-Stack Developer</h2>
        <br />
        <p>
          Welcome to my personal showcase website! Here you'll find information
          about my projects and skills. I aim to keep this space updated with my latest
          work and achievements. I hope you enjoy your visit and that you'll follow
          along with my journey!
        </p>

        <div class="cta-buttons">
          <RouterLink to="/projects" class="cta-button">View My Work</RouterLink>
          <RouterLink to="/contact" class="cta-button">Get in Touch</RouterLink>
        </div>
      </div>
    </section>
  </main>
</template>