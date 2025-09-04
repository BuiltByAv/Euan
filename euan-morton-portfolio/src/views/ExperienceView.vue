<script setup>
import { experiences, earlierRoles } from '@/data/portfolioData'
</script>

<template>
  <div class="experience">
    <div class="container">
      <header class="page-header">
        <h1>Work Experience</h1>
        <p class="page-subtitle">My professional journey and key accomplishments</p>
      </header>

      <div class="timeline">
        <div v-for="job in experiences" :key="job.id" class="timeline-item">
          <div class="timeline-marker"></div>
          <div class="timeline-content">
            <div class="job-card">
              <div class="job-header">
                <h2 class="job-title">{{ job.title }}</h2>
                <div class="company-info">
                  <h3 class="company-name">{{ job.company }}</h3>
                  <div class="job-meta">
                    <span class="period">{{ job.period }}</span>
                    <span class="location">{{ job.location }}</span>
                  </div>
                </div>
              </div>

              <p v-if="job.description" class="job-description">{{ job.description }}</p>

              <div class="achievements-section">
                <h4 class="achievements-title">Key Achievements</h4>
                <ul class="achievements-list">
                  <li v-for="(achievement, index) in job.achievements" :key="index" class="achievement-item">
                    <span class="achievement-bullet">✓</span>
                    <span class="achievement-text">{{ achievement }}</span>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="earlier-roles">
        <h2 class="section-title">Earlier Roles</h2>
        <div class="roles-grid">
          <div v-for="(role, index) in earlierRoles" :key="index" class="role-card">
            <div class="role-header">
              <div class="role-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M20 6L9 17L4 12" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </div>
              <h3 class="role-title">{{ role.title }}</h3>
            </div>
            <p class="role-description">{{ role.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.experience {
  padding: 2rem 0;
  min-height: calc(100vh - 120px);
}

.container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

.page-header {
  text-align: center;
  margin-bottom: 3rem;
}

.page-header h1 {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--color-heading);
  margin-bottom: 0.5rem;
}

.page-subtitle {
  font-size: 1.2rem;
  color: var(--color-text);
  opacity: 0.8;
  margin: 0;
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
  left: 30px;
  width: 3px;
  background: linear-gradient(to bottom, hsla(160, 100%, 37%, 0.8), hsla(160, 100%, 37%, 0.3));
  border-radius: 2px;
}

.timeline-item {
  position: relative;
  margin-bottom: 3rem;
  padding-left: 80px;
}

.timeline-marker {
  position: absolute;
  left: 18px;
  top: 20px;
  width: 24px;
  height: 24px;
  border-radius: 50%;
  background: hsla(160, 100%, 37%, 1);
  border: 4px solid var(--color-background);
  box-shadow: 0 0 0 3px hsla(160, 100%, 37%, 0.3);
  z-index: 2;
}

.timeline-content {
  width: 100%;
}

.job-card {
  background: var(--color-background-soft);
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  border: 1px solid var(--color-border);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.job-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.15);
}

.job-header {
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 2px solid hsla(160, 100%, 37%, 0.2);
}

.job-title {
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--color-heading);
  margin: 0 0 0.5rem 0;
  line-height: 1.3;
}

.company-info {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.company-name {
  font-size: 1.2rem;
  font-weight: 600;
  color: hsla(160, 100%, 37%, 1);
  margin: 0;
}

.job-meta {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  font-size: 0.95rem;
}

.period {
  color: var(--color-text);
  font-weight: 500;
  background: hsla(160, 100%, 37%, 0.1);
  padding: 0.25rem 0.75rem;
  border-radius: 20px;
}

.location {
  color: var(--color-text);
  opacity: 0.8;
}

.job-description {
  font-size: 1.05rem;
  line-height: 1.7;
  color: var(--color-text);
  margin-bottom: 1.5rem;
  font-style: italic;
}

.achievements-section {
  margin-top: 1.5rem;
}

.achievements-title {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--color-heading);
  margin: 0 0 1rem 0;
}

.achievements-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.achievement-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 0.75rem;
  padding: 0.5rem 0;
}

.achievement-bullet {
  color: hsla(160, 100%, 37%, 1);
  font-weight: bold;
  font-size: 1.1rem;
  margin-right: 0.75rem;
  flex-shrink: 0;
  margin-top: 0.1rem;
}

.achievement-text {
  line-height: 1.6;
  color: var(--color-text);
}

.earlier-roles {
  margin-top: 4rem;
  padding: 3rem 2rem 2rem;
  background: linear-gradient(135deg, var(--color-background-mute) 0%, var(--color-background-soft) 100%);
  border-radius: 16px;
  border: 1px solid var(--color-border);
  position: relative;
}

.earlier-roles::before {
  content: '';
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 4px;
  background: linear-gradient(90deg, hsla(160, 100%, 37%, 1), hsla(160, 100%, 45%, 1));
  border-radius: 2px;
}

.section-title {
  font-size: 2rem;
  font-weight: 700;
  color: var(--color-heading);
  text-align: center;
  margin-bottom: 2.5rem;
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 50%;
  transform: translateX(-50%);
  width: 40px;
  height: 2px;
  background: hsla(160, 100%, 37%, 0.5);
  border-radius: 1px;
}

.roles-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

.role-card {
  background: var(--color-background-soft);
  padding: 2rem;
  border-radius: 12px;
  border: 1px solid var(--color-border);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.role-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
  border-color: hsla(160, 100%, 37%, 0.3);
}

.role-header {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 1rem;
  padding-bottom: 0.75rem;
  border-bottom: 2px solid hsla(160, 100%, 37%, 0.2);
}

.role-icon {
  width: 32px;
  height: 32px;
  background: hsla(160, 100%, 37%, 0.1);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: hsla(160, 100%, 37%, 1);
  flex-shrink: 0;
}

.role-title {
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--color-heading);
  margin: 0;
}

.role-description {
  color: var(--color-text);
  line-height: 1.7;
  margin: 0;
  flex-grow: 1;
  font-size: 1.05rem;
}

@media (max-width: 639px) {
  .timeline::before {
    left: 15px;
  }

  .timeline-item {
    padding-left: 50px;
  }

  .timeline-marker {
    left: 6px;
    width: 18px;
    height: 18px;
  }

  .job-card {
    padding: 1.5rem;
  }

  .job-title {
    font-size: 1.2rem;
  }
}

@media (min-width: 640px) {
  .company-info {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .roles-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 768px) {
  .page-header h1 {
    font-size: 3rem;
  }

  .job-title {
    font-size: 1.6rem;
  }
}

@media (min-width: 1024px) {
  .timeline-item {
    padding-left: 100px;
  }

  .timeline::before {
    left: 40px;
  }

  .timeline-marker {
    left: 28px;
  }
}
</style>
