<script setup>
import { projects } from '@/data/projects'
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

        <!-- ===================== SKILLS ===================== -->
    <section id="skills" class="skills-preview">
      <h2 class="section-title">Skills &amp; Technologies</h2>
      <ul class="skills-tiles">
        <li>
          <span class="skill-icon">&lt;/&gt;</span>
          <span class="skill-name">HTML5</span>
        </li>
        <li>
          <span class="skill-icon">#</span>
          <span class="skill-name">CSS3</span>
        </li>
        <li>
          <span class="skill-icon">JS</span>
          <span class="skill-name">JavaScript</span>
        </li>
        <li>
          <span class="skill-icon">▲</span>
          <span class="skill-name">Bootstrap</span>
        </li>
        <li>
          <span class="skill-icon">🐍</span>
          <span class="skill-name">Python</span>
        </li>
        <li>
          <span class="skill-icon">⎇</span>
          <span class="skill-name">Git &amp; GitHub</span>
        </li>
        <li>
          <span class="skill-icon">◐</span>
          <span class="skill-name">Responsive Design</span>
        </li>
        <li>
          <span class="skill-icon">»_</span>
          <span class="skill-name">Command Line</span>
        </li>
      </ul>
    </section>
    
    <!-- ===================== PROJECTS ===================== -->
    <section id="projects" class="projects-section">
      <div style="text-align: center; margin-bottom: 40px;">
        <h2 class="section-title">My Projects</h2>
        <p style="color: rgb(221, 227, 239); max-width: 600px; margin: 20px auto;">
          Here are some of the projects I've built while learning full-stack development.
        </p>
      </div>

      <div class="projects-container">
        <div v-for="project in projects" :key="project.id" class="project-card">
          <div class="card-image" :class="project.imageClass">
            <img :src="project.image" :alt="project.alt" />
          </div>
          <div class="card-content">
            <h3 class="card-title">{{ project.title }}</h3>
            <p class="card-description">{{ project.description }}</p>
            <div class="card-tags">
              <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
            </div>
            <div class="card-footer">
              <a :href="project.link" target="_blank" rel="noopener" class="btn-primary">
                View Project
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>
