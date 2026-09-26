<script setup>
defineProps({
  project: {
    type: Object,
    required: true,
  },
})
</script>

<template>
  <div class="project-card">
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
          Check out this project
        </a>
      </div>
    </div>
  </div>
</template>
