<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <main>
    <!-- ===================== HERO ===================== -->
    <section class="hero-container">
      <div class="hero-content">
        <p class="hero-eyebrow">Hi, I'm</p>
        <h1>Karah <span class="highlight">Fisher</span></h1>
        <h2>Aspiring Full-Stack Developer</h2>
        <p>
          I build clean, thoughtful web experiences while studying at Life Choices
          Academy. From idea to deployment, I turn curiosity into working code — one
          project at a time.
        </p>

        <div class="cta-buttons">
          <RouterLink to="/projects" class="cta-button">View My Work →</RouterLink>
          <RouterLink to="/contact" class="cta-button cta-button--ghost">
            Get in Touch
          </RouterLink>
        </div>
      </div>

      <div class="hero-image">
        <img
          src="https://i.ibb.co/99ny3FSW/Profile-picture.jpg"
          alt="Karah Fisher"
        />
      </div>
    </section>

    <!-- ===================== ABOUT PREVIEW ===================== -->
    <section class="about-preview">
      <div class="about-preview-image">
        <img
          src="https://i.ibb.co/99ny3FSW/Profile-picture.jpg"
          alt="Karah at work"
        />
      </div>
      <div class="about-preview-content">
        <h2 class="section-title">About Me</h2>
        <p>
          Passionate about creating clean, efficient, and scalable solutions with
          great user experiences. I love working with technologies that push the web
          forward — and I'm always learning something new.
        </p>

        <ul class="trait-grid">
          <li>🧩 Problem Solver</li>
          <li>🎯 Detail Oriented</li>
          <li>💻 Clean Code Advocate</li>
          <li>📚 Always Learning</li>
          <li>🤝 Team Player</li>
          <li>🔍 Curious Mind</li>
        </ul>
      </div>
    </section>
  </main>
</template>
