<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { personalInfo } from '@/data/portfolioData'
</script>

<template>
  <header>
    <div class="wrapper">
      <h1 class="site-title">{{ personalInfo.name }}</h1>
      <p class="site-subtitle">{{ personalInfo.title }}</p>

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/experience">Experience</RouterLink>
        <RouterLink to="/skills">Skills</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  background-color: var(--color-background-soft);
  padding: 1.5rem 0;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.wrapper {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.site-title {
  font-size: 2.5rem;
  font-weight: 600;
  margin: 0;
  color: var(--color-heading);
}

.site-subtitle {
  font-size: 1.2rem;
  margin: 0.5rem 0 1.5rem;
  opacity: 0.8;
}

nav {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1.5rem;
  margin-top: 1rem;
}

nav a {
  font-size: 1.1rem;
  font-weight: 500;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  transition: all 0.3s ease;
}

nav a:hover {
  background-color: hsla(160, 100%, 37%, 0.2);
}

nav a.router-link-active {
  color: hsla(160, 100%, 37%, 1);
  border-bottom: 2px solid hsla(160, 100%, 37%, 1);
}

@media (min-width: 768px) {
  .wrapper {
    flex-direction: row;
    justify-content: space-between;
  }
  
  nav {
    margin-top: 0;
  }
  
  .site-title, .site-subtitle {
    text-align: left;
  }
  
  .site-subtitle {
    margin-bottom: 0;
  }
}
</style>

