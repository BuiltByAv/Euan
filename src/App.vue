<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { personalInfo } from '@/data/portfolioData'
</script>

<template>
  <header class="main-header">
    <!-- Background decoration -->
    <div class="header-background">
      <div class="bg-shape bg-shape-1"></div>
      <div class="bg-shape bg-shape-2"></div>
      <div class="bg-shape bg-shape-3"></div>
    </div>

    <div class="wrapper">
      <div class="brand">
        <div class="brand-content">
          <h1 class="site-title">
            <span class="name-highlight">{{ personalInfo.name }}</span>
          </h1>
          <p class="site-subtitle">
            <span class="subtitle-icon">✦</span>
            {{ personalInfo.title }}
            <span class="subtitle-icon">✦</span>
          </p>
        </div>
      </div>

      <nav class="main-nav">
        <div class="nav-container">
          <RouterLink to="/" class="nav-link">
            <span class="nav-text">Home</span>
            <span class="nav-indicator"></span>
          </RouterLink>
          <RouterLink to="/about" class="nav-link">
            <span class="nav-text">About</span>
            <span class="nav-indicator"></span>
          </RouterLink>
          <RouterLink to="/experience" class="nav-link">
            <span class="nav-text">Experience</span>
            <span class="nav-indicator"></span>
          </RouterLink>
          <RouterLink to="/skills" class="nav-link">
            <span class="nav-text">Skills</span>
            <span class="nav-indicator"></span>
          </RouterLink>
          <RouterLink to="/contact" class="nav-link contact-cta">
            <span class="nav-text">Contact</span>
            <span class="nav-indicator"></span>
          </RouterLink>
        </div>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
/* Main Header */
.main-header {
  background: linear-gradient(135deg,
    var(--color-background) 0%,
    var(--color-background-soft) 50%,
    var(--color-background-mute) 100%);
  padding: 1.5rem 0;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 100;
  border-bottom: 1px solid hsla(160, 100%, 37%, 0.2);
  position: relative;
  overflow: hidden;
}

/* Background Decoration */
.header-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  pointer-events: none;
}

.bg-shape {
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(135deg, hsla(160, 100%, 37%, 0.05), hsla(160, 100%, 45%, 0.02));
  animation: float-header 8s ease-in-out infinite;
}

.bg-shape-1 {
  width: 100px;
  height: 100px;
  top: -50px;
  left: 10%;
  animation-delay: 0s;
}

.bg-shape-2 {
  width: 80px;
  height: 80px;
  top: -40px;
  right: 20%;
  animation-delay: 3s;
}

.bg-shape-3 {
  width: 60px;
  height: 60px;
  bottom: -30px;
  left: 70%;
  animation-delay: 6s;
}

@keyframes float-header {
  0%, 100% {
    transform: translateY(0px) rotate(0deg);
  }
  50% {
    transform: translateY(-10px) rotate(180deg);
  }
}

/* Wrapper */
.wrapper {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
  position: relative;
  z-index: 1;
}

/* Brand Section */
.brand {
  text-align: center;
}

.brand-content {
  position: relative;
}

.site-title {
  font-size: 2rem;
  font-weight: 800;
  margin: 0;
  color: var(--color-heading);
  position: relative;
}

.name-highlight {
  background: linear-gradient(135deg, var(--color-heading), hsla(160, 100%, 37%, 1));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  position: relative;
}

.name-highlight::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  right: 0;
  height: 2px;
  background: linear-gradient(90deg, hsla(160, 100%, 37%, 1), hsla(160, 100%, 45%, 1));
  border-radius: 1px;
  animation: glow 2s ease-in-out infinite alternate;
}

@keyframes glow {
  from {
    box-shadow: 0 0 5px hsla(160, 100%, 37%, 0.5);
  }
  to {
    box-shadow: 0 0 15px hsla(160, 100%, 37%, 0.8);
  }
}

.site-subtitle {
  font-size: 1rem;
  margin: 0.5rem 0 0;
  color: var(--color-text);
  font-weight: 500;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
}

.subtitle-icon {
  color: hsla(160, 100%, 37%, 1);
  font-size: 0.8rem;
  animation: sparkle 3s ease-in-out infinite;
}

.subtitle-icon:last-child {
  animation-delay: 1.5s;
}

@keyframes sparkle {
  0%, 100% {
    opacity: 0.5;
    transform: scale(1);
  }
  50% {
    opacity: 1;
    transform: scale(1.2);
  }
}

/* Navigation */
.main-nav {
  width: 100%;
}

.nav-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 0.5rem;
}

.nav-link {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 0.75rem 1.5rem;
  border-radius: 12px;
  font-weight: 600;
  font-size: 1rem;
  transition: all 0.3s ease;
  white-space: nowrap;
  background: var(--color-background);
  border: 2px solid transparent;
  overflow: hidden;
}

.nav-link::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.5s;
}

.nav-link:hover::before {
  left: 100%;
}

.nav-text {
  position: relative;
  z-index: 1;
}

.nav-indicator {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 3px;
  background: linear-gradient(90deg, hsla(160, 100%, 37%, 1), hsla(160, 100%, 45%, 1));
  border-radius: 2px;
  transition: width 0.3s ease;
}

.nav-link:hover {
  transform: translateY(-2px);
  border-color: hsla(160, 100%, 37%, 0.3);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
  background: linear-gradient(135deg, var(--color-background), var(--color-background-soft));
}

.nav-link:hover .nav-indicator {
  width: 80%;
}

.nav-link.router-link-active {
  color: hsla(160, 100%, 37%, 1);
  background: linear-gradient(135deg, hsla(160, 100%, 37%, 0.1), hsla(160, 100%, 45%, 0.05));
  border-color: hsla(160, 100%, 37%, 0.3);
  transform: translateY(-1px);
}

.nav-link.router-link-active .nav-indicator {
  width: 100%;
}

/* Contact CTA Special Styling */
.contact-cta {
  background: linear-gradient(135deg, hsla(160, 100%, 37%, 1), hsla(160, 100%, 45%, 1));
  color: white !important;
  border-color: hsla(160, 100%, 37%, 1);
}

.contact-cta:hover {
  background: linear-gradient(135deg, hsla(160, 100%, 32%, 1), hsla(160, 100%, 40%, 1));
  transform: translateY(-3px);
  box-shadow: 0 10px 30px hsla(160, 100%, 37%, 0.4);
}

.contact-cta .nav-indicator {
  background: white;
}

/* Responsive Design */
@media (min-width: 768px) {
  .wrapper {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .brand {
    text-align: left;
  }

  .site-subtitle {
    justify-content: flex-start;
  }

  .nav-container {
    gap: 1rem;
  }
}

@media (min-width: 1024px) {
  .site-title {
    font-size: 2.5rem;
  }

  .site-subtitle {
    font-size: 1.1rem;
  }

  .nav-container {
    gap: 1.5rem;
  }

  .nav-link {
    padding: 1rem 2rem;
    font-size: 1.1rem;
  }
}

@media (min-width: 1200px) {
  .site-title {
    font-size: 2.8rem;
  }
}
</style>

