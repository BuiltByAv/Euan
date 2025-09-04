<script setup>
import { skillCategories, coreCompetencies, technicalProficiencies } from '@/data/portfolioData'
</script>

<template>
  <div class="skills">
    <div class="container">
      <h1>Skills & Expertise</h1>
      
      <div class="core-competencies">
        <h2>Core Competencies</h2>
        <div class="competencies-list">
          <span v-for="(competency, index) in coreCompetencies" :key="index" class="competency-tag">
            {{ competency }}
          </span>
        </div>
      </div>
      
      <div class="skills-container">
        <div v-for="category in skillCategories" :key="category.id" class="skill-category">
          <h2>{{ category.name }}</h2>
          
          <div class="skill-list">
            <div v-for="skill in category.skills" :key="skill.name" class="skill-item">
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-level">{{ skill.level }}%</span>
              </div>
              <div class="skill-bar">
                <div class="skill-progress" :style="{ width: skill.level + '%' }"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="technical-proficiencies">
        <h2>Technical Proficiencies</h2>
        <div class="tech-grid">
          <div v-for="(tech, index) in technicalProficiencies" :key="index" class="tech-item">
            <span class="tech-name">{{ tech.name }}</span>
            <span v-if="tech.details" class="tech-details">{{ tech.details }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.skills {
  padding: 2rem 0;
}

.container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 1rem;
}

h1 {
  margin-bottom: 2rem;
  text-align: center;
}

.skills-container {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

.skill-category {
  background-color: var(--color-background-soft);
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

h2 {
  margin-top: 0;
  margin-bottom: 1.5rem;
  font-size: 1.5rem;
  color: hsla(160, 100%, 37%, 1);
}

.skill-list {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.skill-info {
  display: flex;
  justify-content: space-between;
  margin-bottom: 0.5rem;
}

.skill-name {
  font-weight: 500;
}

.skill-level {
  opacity: 0.7;
}

.skill-bar {
  height: 8px;
  background-color: var(--color-background-mute);
  border-radius: 4px;
  overflow: hidden;
}

.skill-progress {
  height: 100%;
  background-color: hsla(160, 100%, 37%, 1);
  border-radius: 4px;
}

@media (min-width: 768px) {
  .skills-container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .skills-container {
    grid-template-columns: repeat(3, 1fr);
  }
}

.core-competencies {
  margin-bottom: 2rem;
  background-color: var(--color-background-soft);
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.competencies-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.competency-tag {
  background-color: hsla(160, 100%, 37%, 0.1);
  color: hsla(160, 100%, 37%, 1);
  padding: 0.5rem 1rem;
  border-radius: 4px;
  font-size: 0.9rem;
}

.technical-proficiencies {
  margin-top: 2rem;
  background-color: var(--color-background-soft);
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.tech-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 1rem;
}

.tech-item {
  display: flex;
  flex-direction: column;
}

.tech-name {
  font-weight: 500;
}

.tech-details {
  font-size: 0.8rem;
  opacity: 0.7;
}
</style>
