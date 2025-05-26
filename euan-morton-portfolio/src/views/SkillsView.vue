<script setup>
// Sample data - replace with Euan's actual skills
const skillCategories = [
  {
    id: 1,
    name: 'Product Management',
    skills: [
      { name: 'Product Strategy', level: 90 },
      { name: 'Roadmap Planning', level: 85 },
      { name: 'User Research', level: 80 },
      { name: 'A/B Testing', level: 75 },
      { name: 'Product Analytics', level: 85 }
    ]
  },
  {
    id: 2,
    name: 'Technical Skills',
    skills: [
      { name: 'Agile Methodologies', level: 90 },
      { name: 'JIRA', level: 85 },
      { name: 'SQL', level: 70 },
      { name: 'Wireframing', level: 75 },
      { name: 'Product Requirements', level: 95 }
    ]
  },
  {
    id: 3,
    name: 'Soft Skills',
    skills: [
      { name: 'Leadership', level: 85 },
      { name: 'Communication', level: 90 },
      { name: 'Stakeholder Management', level: 85 },
      { name: 'Problem Solving', level: 90 },
      { name: 'Team Collaboration', level: 95 }
    ]
  }
]
</script>

<template>
  <div class="skills">
    <div class="container">
      <h1>Skills & Expertise</h1>
      
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
</style>