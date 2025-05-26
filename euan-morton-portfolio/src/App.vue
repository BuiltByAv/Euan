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
/* Styles remain the same */
</style>



