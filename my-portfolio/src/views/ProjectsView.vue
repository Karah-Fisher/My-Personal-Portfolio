<script setup>
import { projects } from '@/data/projects'
import ProjectCard from '@/components/ProjectCard.vue'
</script>

<template>
  <main>
    <section class="projects-section">
      <h1>My Projects &amp; Skills</h1>
      <p>Here are some of the projects I've made.</p>

      <div class="projects-container">
        <ProjectCard v-for="project in projects" :key="project.id" :project="project" />
      </div>
    </section>
  </main>
</template>
