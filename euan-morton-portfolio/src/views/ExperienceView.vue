<script setup>
import { experiences, earlierRoles } from '@/data/portfolioData'
</script>

<template>
  <div class="experience">
    <div class="container">
      <h1>Work Experience</h1>
      
      <div class="timeline">
        <div v-for="job in experiences" :key="job.id" class="timeline-item">
          <div class="timeline-content">
            <div class="job-header">
              <h2>{{ job.title }}</h2>
              <h3>{{ job.company }}</h3>
              <span class="period">{{ job.period }} | {{ job.location }}</span>
            </div>
            
            <p v-if="job.description">{{ job.description }}</p>
            
            <h4>Key Achievements:</h4>
            <ul>
              <li v-for="(achievement, index) in job.achievements" :key="index">
                {{ achievement }}
              </li>
            </ul>
          </div>
        </div>
      </div>
      
      <div class="earlier-roles">
        <h2>Earlier Roles</h2>
        <div v-for="(role, index) in earlierRoles" :key="index" class="role-item">
          <h3>{{ role.title }}</h3>
          <p>{{ role.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.experience {
  padding: 2rem 0;
}

.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 0 1rem;
}

h1 {
  margin-bottom: 2rem;
  text-align: center;
}

.timeline {
  position: relative;
  padding: 2rem 0;
}

.timeline::before {
  content: '';
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  width: 2px;
  background-color: hsla(160, 100%, 37%, 0.5);
  display: none;
}

.timeline-item {
  margin-bottom: 3rem;
  position: relative;
  padding: 1.5rem;
  border-radius: 8px;
  background-color: var(--color-background-soft);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.job-header {
  margin-bottom: 1rem;
}

h2 {
  margin: 0;
  font-size: 1.5rem;
}

h3 {
  margin: 0.5rem 0 0;
  font-size: 1.2rem;
  font-weight: 500;
}

.period {
  display: block;
  font-size: 0.9rem;
  color: var(--color-text);
  opacity: 0.7;
  margin-top: 0.25rem;
}

p {
  line-height: 1.6;
  margin-bottom: 1rem;
}

h4 {
  margin: 1.5rem 0 0.5rem;
}

ul {
  padding-left: 1.5rem;
  line-height: 1.6;
}

@media (min-width: 768px) {
  .timeline::before {
    display: block;
    left: 20%;
  }
  
  .timeline-item {
    padding-left: calc(20% + 2rem);
  }
  
  .timeline-item::before {
    content: '';
    position: absolute;
    left: 20%;
    top: 1.5rem;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background-color: hsla(160, 100%, 37%, 1);
    transform: translateX(-50%);
  }
}

.earlier-roles {
  margin-top: 3rem;
  padding-top: 2rem;
  border-top: 1px solid var(--color-border);
}

.role-item {
  margin-bottom: 1.5rem;
}

.role-item h3 {
  margin-bottom: 0.5rem;
}
</style>
