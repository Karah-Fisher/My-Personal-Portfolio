<script setup>
defineProps({
  skill: Object,
})
</script>

<template>
  <div class="skill">
    <div class="skill-header">
      <span>{{ skill.name }}</span>
      <span>{{ skill.level }}%</span>
    </div>
    <div class="bar">
      <div class="fill" :style="{ width: skill.level + '%' }"></div>
    </div>
  </div>
</template>

<style scoped>
.skill {
  margin-bottom: 1rem;
}
.skill-header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 0.25rem;
  font-size: 0.9rem;
}
.bar {
  height: 8px;
  background: #e5e7eb;
  border-radius: 999px;
  overflow: hidden;
}
.fill {
  height: 100%;
  background: linear-gradient(90deg, #6366f1, #8b5cf6);
  transition: width 0.6s ease;
}
</style>
