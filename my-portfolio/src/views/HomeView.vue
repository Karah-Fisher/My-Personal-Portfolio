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

            <!-- ===================== SKILLS & TECHNOLOGIES ===================== -->
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

        <!-- ===================== CONTACT ===================== -->
    <section id="contact" class="contact-section">
      <h2 class="section-title" style="text-align: center; margin-bottom: 40px;">Contact Me</h2>
      <p style="text-align: center; color: rgb(221, 227, 239);">Feel free to reach out by filling out the form below.</p>
      
      <!-- MY FORMSPREE LINK -->
      <form action="https://formspree.io/f/mpqnvozl" method="POST">
        <div>
          <label for="name">Name:</label>
          <input type="text" id="name" name="name" required placeholder="Your Name" />
        </div>
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" name="email" required placeholder="your.email@example.com" />
        </div>
        <div>
          <label for="subject">Subject:</label>
          <input type="text" id="subject" name="subject" required placeholder="Project inquiry" />
        </div>
        <div>
          <label for="message">Message:</label>
          <textarea id="message" name="message" rows="5" required placeholder="Tell me about your project..."></textarea>
        </div>
        <button type="submit">Send Message</button>
      </form>

      <div class="social-media-section">
        <h3>Connect with Me</h3>
        <ul class="social-media-list">
          <li>
            <a class="social-btn" href="https://www.linkedin.com/in/karah-fisher/" target="_blank" rel="noopener">
              LinkedIn
            </a>
          </li>
          <li>
            <a class="social-btn" href="https://github.com/Karah-Fisher" target="_blank" rel="noopener">
              GitHub
            </a>
          </li>
        </ul>
      </div>
    </section>

  </main>
</template>
