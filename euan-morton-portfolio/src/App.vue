<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { personalInfo } from '@/data/portfolioData'
</script>

<template>
  <header>
    <div class="wrapper">
      <div class="brand">
        <h1 class="site-title">{{ personalInfo.name }}</h1>
        <p class="site-subtitle">{{ personalInfo.title }}</p>
      </div>

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
  padding: 1rem 0;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 100;
}

.wrapper {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.brand {
  text-align: center;
}

.site-title {
  font-size: 1.8rem;
  font-weight: 600;
  margin: 0;
  color: var(--color-heading);
}

.site-subtitle {
  font-size: 0.9rem;
  margin: 0.25rem 0 0;
  opacity: 0.7;
  font-weight: 400;
}

nav {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1.5rem;
}

nav a {
  font-size: 1rem;
  font-weight: 500;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  transition: all 0.3s ease;
  white-space: nowrap;
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
    align-items: center;
  }

  .brand {
    text-align: left;
  }

  .site-title {
    font-size: 2rem;
  }

  .site-subtitle {
    font-size: 1rem;
  }
}

@media (min-width: 1024px) {
  .site-title {
    font-size: 2.2rem;
  }

  .site-subtitle {
    font-size: 1.1rem;
  }
}
</style>

