<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <h1 class="site-title">Euan Morton</h1>
      <p class="site-subtitle">Product Manager</p>

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
  line-height: 1.5;
  padding: 1.5rem 0;
}

.wrapper {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.site-title {
  font-size: 2rem;
  font-weight: 700;
  margin: 0;
  color: var(--color-heading);
}

.site-subtitle {
  font-size: 1.2rem;
  margin: 0.5rem 0 1.5rem;
  color: var(--color-text);
  opacity: 0.8;
}

nav {
  width: 100%;
  text-align: center;
  margin-top: 1.5rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

nav a {
  display: inline-block;
  padding: 0.5rem 1rem;
  margin: 0.25rem;
  border-radius: 4px;
  transition: background-color 0.3s;
}

nav a.router-link-active {
  color: var(--color-text);
  background-color: rgba(60, 60, 60, 0.1);
}

@media (min-width: 768px) {
  nav {
    justify-content: flex-start;
  }
}

@media (min-width: 1024px) {
  header .wrapper {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  nav {
    margin-top: 1rem;
  }
}
</style>

