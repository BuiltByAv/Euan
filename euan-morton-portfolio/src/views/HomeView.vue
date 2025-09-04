<script setup>
import { personalInfo } from '@/data/portfolioData'
</script>

<template>
  <main>
    <section class="hero">
      <div class="container">
        <h1>{{ personalInfo.name }}</h1>
        <h2>{{ personalInfo.title }}</h2>
        <div class="intro">
          <p v-for="(paragraph, index) in personalInfo.summary" :key="index">
            {{ paragraph }}
          </p>
        </div>
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
  min-height: calc(100vh - 120px);
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 2rem 0;
}

.container {
  width: 100%;
  max-width: 900px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 0.75rem;
  font-weight: 700;
  color: var(--color-heading);
  line-height: 1.2;
}

h2 {
  font-size: 1.25rem;
  font-weight: 400;
  margin-bottom: 2.5rem;
  opacity: 0.8;
  color: var(--color-text);
}

.intro {
  font-size: 1.1rem;
  line-height: 1.7;
  margin-bottom: 3rem;
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
  color: var(--color-text);
}

.intro p {
  margin-bottom: 1rem;
}

.intro p:last-child {
  margin-bottom: 0;
}

.cta-buttons {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  align-items: center;
}

.cta-button {
  padding: 0.875rem 2rem;
  border-radius: 6px;
  font-weight: 600;
  font-size: 1rem;
  transition: all 0.3s ease;
  text-decoration: none;
  display: inline-block;
  min-width: 160px;
  text-align: center;
}

.primary {
  background-color: hsla(160, 100%, 37%, 1);
  color: white;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.primary:hover {
  background-color: hsla(160, 100%, 32%, 1);
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
}

.secondary {
  border: 2px solid hsla(160, 100%, 37%, 1);
  color: hsla(160, 100%, 37%, 1);
  background-color: transparent;
}

.secondary:hover {
  background-color: hsla(160, 100%, 37%, 1);
  color: white;
  transform: translateY(-2px);
}

@media (min-width: 640px) {
  .cta-buttons {
    flex-direction: row;
    justify-content: center;
    gap: 1.5rem;
  }
}

@media (min-width: 768px) {
  h1 {
    font-size: 3.5rem;
  }

  h2 {
    font-size: 1.5rem;
  }

  .intro {
    font-size: 1.2rem;
  }
}

@media (min-width: 1024px) {
  h1 {
    font-size: 4rem;
  }

  h2 {
    font-size: 1.75rem;
  }

  .hero {
    text-align: left;
  }

  .intro {
    margin-left: 0;
    margin-right: 0;
  }

  .cta-buttons {
    justify-content: flex-start;
  }
}

@media (min-width: 1200px) {
  h1 {
    font-size: 4.5rem;
  }
}
</style>




