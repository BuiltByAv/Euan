<script setup>
import { personalInfo } from '@/data/portfolioData'
</script>

<template>
  <main>
    <section class="hero">
      <div class="container">
        <h1>{{ personalInfo.name }}</h1>
        <h2>{{ personalInfo.title }}</h2>
        <p class="intro">
          {{ personalInfo.summary[0] }}
        </p>
        <div class="cta-buttons">
          <RouterLink to="/contact" class="cta-button primary">Get in Touch</RouterLink>
          <RouterLink to="/experience" class="cta-button secondary">View My Work</RouterLink>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
.hero {
  min-height: 80vh;
  display: flex;
  align-items: center;
  text-align: center;
}

.container {
  width: 100%;
  max-width: 800px;
  margin: 0 auto;
  padding: 0 1rem;
}

h1 {
  font-size: 3rem;
  margin-bottom: 0.5rem;
}

h2 {
  font-size: 1.5rem;
  font-weight: 400;
  margin-bottom: 2rem;
  opacity: 0.8;
}

.intro {
  font-size: 1.25rem;
  line-height: 1.6;
  margin-bottom: 2.5rem;
}

.cta-buttons {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  align-items: center;
}

.cta-button {
  padding: 0.75rem 1.5rem;
  border-radius: 4px;
  font-weight: 500;
  transition: all 0.3s ease;
}

.primary {
  background-color: hsla(160, 100%, 37%, 1);
  color: white;
}

.secondary {
  border: 1px solid hsla(160, 100%, 37%, 1);
  color: hsla(160, 100%, 37%, 1);
}

@media (min-width: 640px) {
  .cta-buttons {
    flex-direction: row;
    justify-content: center;
  }
}

@media (min-width: 1024px) {
  h1 {
    font-size: 4rem;
  }
  
  h2 {
    font-size: 2rem;
  }
  
  .hero {
    text-align: left;
  }
  
  .cta-buttons {
    justify-content: flex-start;
  }
}
</style>


