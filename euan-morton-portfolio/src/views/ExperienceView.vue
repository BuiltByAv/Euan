<script setup>
// Sample data - replace with Euan's actual experience
const experiences = [
  {
    id: 1,
    title: 'Senior Product Manager',
    company: 'Company Name',
    period: 'Jan 2021 - Present',
    description: 'Led the development of [product/feature], resulting in [specific achievements]. Collaborated with cross-functional teams to deliver solutions that increased user engagement by X%.',
    achievements: [
      'Launched X new features that increased user retention by Y%',
      'Led a team of X designers and engineers',
      'Established product metrics and KPIs that improved decision-making'
    ]
  },
  {
    id: 2,
    title: 'Product Manager',
    company: 'Previous Company',
    period: 'Mar 2018 - Dec 2020',
    description: 'Managed the product lifecycle from conception to launch for [product]. Worked closely with engineering, design, and marketing teams to ensure alignment with business goals.',
    achievements: [
      'Increased product revenue by X% year-over-year',
      'Reduced development time by implementing agile methodologies',
      'Conducted user research that informed product roadmap'
    ]
  }
]
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
              <span class="period">{{ job.period }}</span>
            </div>
            
            <p>{{ job.description }}</p>
            
            <h4>Key Achievements:</h4>
            <ul>
              <li v-for="(achievement, index) in job.achievements" :key="index">
                {{ achievement }}
              </li>
            </ul>
          </div>
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
</style>