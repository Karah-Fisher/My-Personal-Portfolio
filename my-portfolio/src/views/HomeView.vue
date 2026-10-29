<script setup>
import { ref} from 'vue'
import { projects } from '@/data/projects'
import { certificates } from '@/data/certificates'
import { skillGroups } from '@/data/skills'


// Certificate Modal State
const selectedCert = ref(null)
const openCertModal = (cert) => { selectedCert.value = cert }
const closeCertModal = () => { selectedCert.value = null }
</script>

<template>
  <main>
    <!-- ===================== HERO ===================== -->
    <section id="top" class="hero-container">
      <div class="hero-content">
        <p class="hero-eyebrow">Hi, I'm</p>
        <h1>Karah <span class="highlight">Fisher</span></h1>
        <h2>Junior Full-Stack Web Developer</h2>
        <p>
          I build clean, thoughtful web experiences that are user-focused and have practical
          functionality. From idea to deployment, I turn curiosity into working code — one project
          at a time.
        </p>

        <div class="cta-buttons">
          <a href="#projects" class="cta-button cta-button--ghost">View My Work →</a>
          <a href="/Karah-Fisher-Resume.pdf" class="cta-button cta-button--ghost" download> Download CV ↓ </a>
        </div>
      </div>
    </section>

    <!-- ===================== ABOUT PREVIEW ===================== -->
    <section id="about" class="about-preview">
      <div class="about-preview-image">
        <img src="https://i.ibb.co/99ny3FSW/Profile-picture.jpg" alt="Karah at work" />
      </div>
      <div class="about-preview-content">
        <div class="section-header">
          <p class="eyebrow">Discovery</p>
          <h2 class="section-title">About Me</h2>
        </div>
        <p>
          I am passionate about creating clean, efficient, and scalable solutions with great user
          experiences. I recently graduated from an intensive, 6 month full-stack web development
          course, and I'm ready to bring my skills to a team that values collaboration, creativity,
          and continuous learning. I love working with technologies that push the web forward — and
          I'm always learning something new.
        </p>

        <ul class="trait-grid">
          <li>Problem Solver</li>
          <li>Detail Oriented</li>
          <li>Clean Code Advocate</li>
          <li>Always Learning</li>
          <li>Team Player</li>
          <li>Curious Mind</li>
        </ul>
      </div>
    </section>

    <!-- ===================== SKILLS & TECHNOLOGIES ===================== -->
    <section id="skills" class="skills-preview">
      <div class="section-header">
        <p class="eyebrow">Tech Stack</p>
        <h2 class="section-title">Specialized Skillset</h2>
      </div>

      <div class="skills-grid-layout">
        <!-- Loop through each category -->
        <div v-for="group in skillGroups" :key="group.category" class="skill-group-card">
          <!-- Category Header -->
          <div class="skill-group-header">
            <span class="group-icon" v-html="group.icon"></span>
            <h3>{{ group.category }}</h3>
          </div>

          <!-- Category Grid of Skills -->
          <div class="skill-items-grid">
            <div v-for="skill in group.skills" :key="skill.name" class="skill-item">
              <i :class="skill.icon" class="skill-icon"></i>
              <span class="skill-name">{{ skill.name }}</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ===================== PROJECTS ===================== -->
    <section id="projects" class="projects-section">
      <div style="text-align: center; margin-bottom: 40px">
        <p class="eyebrow">Portfolio</p>
        <h2 class="section-title">My Projects</h2>
        <p style="color: rgb(221, 227, 239); max-width: 600px; margin: 20px auto">
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

    <!-- ===================== CERTIFICATES ===================== -->
    <section id="certificates" class="certificates-section">
      <div class="section-header">
        <p class="eyebrow">Skills Validation</p>
        <h2 class="section-title">Certificates</h2>
      </div>

      <div class="certificates-grid">
        <div v-for="cert in certificates" :key="cert.id" class="cert-card" @click="openCertModal(cert)">
          <div class="cert-icon">{{ cert.icon }}</div>
          <h3 class="cert-title">{{ cert.title }}</h3>
          <p class="cert-issuer">{{ cert.issuer }}</p>
          <p class="cert-date">{{ cert.date }}</p>

          <!-- To add a subtle hint that is clickable -->
           <span class="cert-view-btn">View Certificate</span>
        </div>
      </div>
    </section>

        <!-- ===================== CERTIFICATE MODAL ===================== -->
    <div v-if="selectedCert" class="modal-overlay" @click.self="closeCertModal">
      <div class="modal-content cert-modal-content">
        <button class="modal-close" @click="closeCertModal">✕</button>
        
        <img :src="selectedCert.image" :alt="selectedCert.title" class="cert-modal-img" />
        
        <div class="cert-modal-body" style="padding: 30px; display: flex; flex-direction: column; align-items: center; gap: 10px;">
          <h2 style="color: var(--text-main); font-size: 1.5rem; margin: 0;">{{ selectedCert.title }}</h2>
          <p style="color: var(--text-muted); margin: 0;">
            Issued by <strong style="color: var(--accent);">{{ selectedCert.issuer }}</strong>
          </p>
        </div>
      </div>
    </div>



    <!-- ===================== CONTACT ===================== -->
    <section id="contact" class="contact-section">
      <div class="contact-container">
        <!-- Left Side: Text & Contact Details -->
        <div class="contact-info">
          <p class="eyebrow">Connect</p>
          <h2 class="contact-title">Let's build<br />together</h2>
          <p class="contact-desc">
            Open to freelance opportunities, consulting, and full-time collaborative projects. Drop
            me a line and let's start a conversation.
          </p>
          
          <!-- Contact Links (We're going to use SVG icons to better match the red theme!)-->
          <div class="contact-links">
            <!-- Email -->
            <div class="contact-item">
              <div class="contact-icon">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
              </div>
              <div>
                <p class="contact-label">EMAIL ME</p>
                <a href="mailto:hello@karahfisher.dev" class="contact-value">hello@karahfisher.dev</a>
              </div>
            </div>

            <!-- LinkedIn -->
            <div class="contact-item">
              <div class="contact-icon">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
              </div>
              <div>
                <p class="contact-label">LINKEDIN</p>
                <a href="https://www.linkedin.com/in/karah-fisher/" target="_blank" class="contact-value">linkedin.com/in/karah-fisher</a>
              </div>
            </div>

            <!-- GitHub -->
            <div class="contact-item">
              <div class="contact-icon">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
              </div>
              <div>
                <p class="contact-label">GITHUB</p>
                <a href="https://github.com/Karah-Fisher" target="_blank" class="contact-value">github.com/Karah-Fisher</a>
              </div>
            </div>
          </div>
        </div>

        <!-- Right Side: The Form -->
        <div class="contact-form-wrapper">
          <form action="https://formspree.io/f/mpqnvozl" method="POST">
            <div class="form-row">
              <div class="form-group">
                <label for="name">FULL NAME</label>
                <input type="text" id="name" name="name" required placeholder="John Doe" />
              </div>
              <div class="form-group">
                <label for="email">EMAIL ADDRESS</label>
                <input
                  type="email"
                  id="email"
                  name="email"
                  required
                  placeholder="john@example.com"
                />
              </div>
            </div>

            <div class="form-group">
              <label for="subject">SUBJECT</label>
              <input
                type="text"
                id="subject"
                name="subject"
                required
                placeholder="Project Inquiry"
              />
            </div>

            <div class="form-group">
              <label for="message">MESSAGE</label>
              <textarea
                id="message"
                name="message"
                rows="5"
                required
                placeholder="Tell me about your project..."
              ></textarea>
            </div>

            <button type="submit" class="submit-btn">SEND MESSAGE</button>
          </form>
        </div>
      </div>
    </section>
  </main>
</template>
