<script setup>
import { personalInfo } from '@/data/portfolioData'
</script>

<template>
  <main>
    <section class="hero">
      <!-- Animated background elements -->
      <div class="hero-background">
        <div class="floating-shapes">
          <div class="shape shape-1"></div>
          <div class="shape shape-2"></div>
          <div class="shape shape-3"></div>
          <div class="shape shape-4"></div>
        </div>
      </div>

      <div class="container">
        <div class="hero-content">
          <!-- Left side - Content -->
          <div class="hero-text">
            <div class="hero-badge">
              <span class="badge-dot"></span>
              <span class="badge-text">Available for New Opportunities</span>
            </div>

            <h1 class="hero-title">
              <span class="title-line">Hello, I'm</span>
              <span class="title-name">{{ personalInfo.name }}</span>
              <span class="title-accent">.</span>
            </h1>

            <h2 class="hero-subtitle">{{ personalInfo.title }}</h2>

            <div class="hero-intro">
              <p v-for="(paragraph, index) in personalInfo.summary" :key="index" class="intro-paragraph">
                {{ paragraph }}
              </p>
            </div>

            <div class="hero-stats">
              <div class="stat-item">
                <span class="stat-number">10+</span>
                <span class="stat-label">Years Experience</span>
              </div>
              <div class="stat-item">
                <span class="stat-number">2x</span>
                <span class="stat-label">Faster Delivery</span>
              </div>
              <div class="stat-item">
                <span class="stat-number">50+</span>
                <span class="stat-label">Teams Coached</span>
              </div>
            </div>

            <div class="cta-buttons">
              <RouterLink to="/contact" class="cta-button primary">
                <span class="button-text">Get in Touch</span>
                <span class="button-icon">→</span>
              </RouterLink>
              <RouterLink to="/experience" class="cta-button secondary">
                <span class="button-text">View My Work</span>
                <span class="button-icon">→</span>
              </RouterLink>
            </div>

            <div class="social-proof">
              <p class="social-text">Trusted by leading organizations</p>
              <div class="company-logos">
                <span class="company-name">US Bank</span>
                <span class="company-name">Availabie</span>
                <span class="company-name">Rochester, NY</span>
              </div>
            </div>
          </div>

          <!-- Right side - Professional Image -->
          <div class="hero-image">
            <div class="image-container">
              <div class="image-placeholder">
                <div class="image-content">
                  <div class="profile-icon">
                    <svg width="120" height="120" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                      <path d="M20 21V19C20 17.9391 19.5786 16.9217 18.8284 16.1716C18.0783 15.4214 17.0609 15 16 15H8C6.93913 15 5.92172 15.4214 5.17157 16.1716C4.42143 16.9217 4 17.9391 4 19V21" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                      <path d="M12 11C14.2091 11 16 9.20914 16 7C16 4.79086 14.2091 3 12 3C9.79086 3 8 4.79086 8 7C8 9.20914 9.79086 11 12 11Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                    </svg>
                  </div>
                  <p class="image-text">Professional Photo</p>
                  <p class="image-subtext">Can you send me a photo of you again</p>
                </div>
              </div>
              <div class="image-decorations">
                <div class="decoration decoration-1"></div>
                <div class="decoration decoration-2"></div>
                <div class="decoration decoration-3"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
/* Hero Section */
.hero {
  min-height: calc(100vh - 120px);
  position: relative;
  display: flex;
  align-items: center;
  padding: 2rem 0;
  overflow: hidden;
}

/* Animated Background */
.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 0;
}

.floating-shapes {
  position: absolute;
  width: 100%;
  height: 100%;
}

.shape {
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(135deg, hsla(160, 100%, 37%, 0.1), hsla(160, 100%, 45%, 0.05));
  animation: float 6s ease-in-out infinite;
}

.shape-1 {
  width: 80px;
  height: 80px;
  top: 20%;
  left: 10%;
  animation-delay: 0s;
}

.shape-2 {
  width: 120px;
  height: 120px;
  top: 60%;
  right: 15%;
  animation-delay: 2s;
}

.shape-3 {
  width: 60px;
  height: 60px;
  top: 80%;
  left: 20%;
  animation-delay: 4s;
}

.shape-4 {
  width: 100px;
  height: 100px;
  top: 10%;
  right: 30%;
  animation-delay: 1s;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px) rotate(0deg);
  }
  50% {
    transform: translateY(-20px) rotate(180deg);
  }
}

/* Container */
.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
  position: relative;
  z-index: 1;
}

/* Hero Content Layout */
.hero-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: 3rem;
  align-items: center;
}

/* Hero Text Section */
.hero-text {
  text-align: center;
}

/* Hero Badge */
.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: linear-gradient(135deg, hsla(160, 100%, 37%, 0.1), hsla(160, 100%, 45%, 0.05));
  border: 1px solid hsla(160, 100%, 37%, 0.2);
  padding: 0.5rem 1rem;
  border-radius: 50px;
  margin-bottom: 2rem;
  animation: pulse 2s infinite;
}

.badge-dot {
  width: 8px;
  height: 8px;
  background: hsla(160, 100%, 37%, 1);
  border-radius: 50%;
  animation: pulse-dot 2s infinite;
}

@keyframes pulse-dot {
  0%, 100% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.7;
    transform: scale(1.2);
  }
}

.badge-text {
  font-size: 0.9rem;
  font-weight: 500;
  color: hsla(160, 100%, 37%, 1);
}

@keyframes pulse {
  0%, 100% {
    box-shadow: 0 0 0 0 hsla(160, 100%, 37%, 0.4);
  }
  50% {
    box-shadow: 0 0 0 10px hsla(160, 100%, 37%, 0);
  }
}

/* Hero Title */
.hero-title {
  font-size: 2.5rem;
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 1rem;
  color: var(--color-heading);
}

.title-line {
  display: block;
  font-size: 0.6em;
  font-weight: 500;
  opacity: 0.8;
  margin-bottom: 0.5rem;
}

.title-name {
  display: block;
  background: linear-gradient(135deg, var(--color-heading), hsla(160, 100%, 37%, 1));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.title-accent {
  color: hsla(160, 100%, 37%, 1);
  animation: blink 2s infinite;
}

@keyframes blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}

/* Hero Subtitle */
.hero-subtitle {
  font-size: 1.3rem;
  font-weight: 500;
  color: var(--color-text);
  opacity: 0.9;
  margin-bottom: 2rem;
}

/* Hero Intro */
.hero-intro {
  max-width: 600px;
  margin: 0 auto 2.5rem;
}

.intro-paragraph {
  font-size: 1.1rem;
  line-height: 1.7;
  color: var(--color-text);
  margin-bottom: 1rem;
}

.intro-paragraph:last-child {
  margin-bottom: 0;
}

/* Hero Stats */
.hero-stats {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-bottom: 2.5rem;
  flex-wrap: wrap;
}

.stat-item {
  text-align: center;
}

.stat-number {
  display: block;
  font-size: 2rem;
  font-weight: 700;
  color: hsla(160, 100%, 37%, 1);
  line-height: 1;
}

.stat-label {
  display: block;
  font-size: 0.9rem;
  color: var(--color-text);
  opacity: 0.8;
  margin-top: 0.25rem;
}

/* CTA Buttons */
.cta-buttons {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  align-items: center;
  margin-bottom: 3rem;
}

.cta-button {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 2rem;
  border-radius: 12px;
  font-weight: 600;
  font-size: 1rem;
  text-decoration: none;
  transition: all 0.3s ease;
  min-width: 180px;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.cta-button::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.5s;
}

.cta-button:hover::before {
  left: 100%;
}

.primary {
  background: linear-gradient(135deg, hsla(160, 100%, 37%, 1), hsla(160, 100%, 45%, 1));
  color: white;
  box-shadow: 0 4px 20px hsla(160, 100%, 37%, 0.3);
}

.primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 30px hsla(160, 100%, 37%, 0.4);
}

.secondary {
  border: 2px solid hsla(160, 100%, 37%, 1);
  color: hsla(160, 100%, 37%, 1);
  background: transparent;
}

.secondary:hover {
  background: hsla(160, 100%, 37%, 1);
  color: white;
  transform: translateY(-3px);
}

.button-icon {
  font-size: 1.2rem;
  transition: transform 0.3s ease;
}

.cta-button:hover .button-icon {
  transform: translateX(3px);
}

/* Social Proof */
.social-proof {
  text-align: center;
}

.social-text {
  font-size: 0.9rem;
  color: var(--color-text);
  opacity: 0.7;
  margin-bottom: 1rem;
}

.company-logos {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.company-name {
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--color-text);
  opacity: 0.6;
  padding: 0.5rem 1rem;
  border: 1px solid var(--color-border);
  border-radius: 20px;
  background: var(--color-background-soft);
}

/* Hero Image Section */
.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

.image-container {
  position: relative;
  width: 300px;
  height: 300px;
}

.image-placeholder {
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, var(--color-background-soft), var(--color-background-mute));
  border-radius: 20px;
  border: 2px solid var(--color-border);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.image-placeholder::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: linear-gradient(45deg, transparent, hsla(160, 100%, 37%, 0.1), transparent);
  animation: shimmer 3s infinite;
}

@keyframes shimmer {
  0% {
    transform: translateX(-100%) translateY(-100%) rotate(45deg);
  }
  100% {
    transform: translateX(100%) translateY(100%) rotate(45deg);
  }
}

.image-content {
  text-align: center;
  z-index: 1;
}

.profile-icon {
  color: hsla(160, 100%, 37%, 0.6);
  margin-bottom: 1rem;
}

.image-text {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--color-heading);
  margin-bottom: 0.5rem;
}

.image-subtext {
  font-size: 0.9rem;
  color: var(--color-text);
  opacity: 0.7;
  margin: 0;
}

/* Image Decorations */
.image-decorations {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  pointer-events: none;
}

.decoration {
  position: absolute;
  border-radius: 50%;
  background: hsla(160, 100%, 37%, 0.2);
}

.decoration-1 {
  width: 20px;
  height: 20px;
  top: 20px;
  right: 20px;
  animation: float 4s ease-in-out infinite;
}

.decoration-2 {
  width: 15px;
  height: 15px;
  bottom: 30px;
  left: 30px;
  animation: float 5s ease-in-out infinite reverse;
}

.decoration-3 {
  width: 25px;
  height: 25px;
  top: 50%;
  right: 10px;
  animation: float 6s ease-in-out infinite;
  animation-delay: 2s;
}

/* Responsive Design */
@media (min-width: 640px) {
  .cta-buttons {
    flex-direction: row;
    justify-content: center;
    gap: 1.5rem;
  }

  .hero-stats {
    gap: 3rem;
  }
}

@media (min-width: 768px) {
  .hero-title {
    font-size: 3.5rem;
  }

  .hero-subtitle {
    font-size: 1.5rem;
  }

  .intro-paragraph {
    font-size: 1.2rem;
  }
}

@media (min-width: 1024px) {
  .hero-content {
    grid-template-columns: 1fr 400px;
    gap: 4rem;
  }

  .hero-text {
    text-align: left;
  }

  .hero-intro {
    margin-left: 0;
    margin-right: 0;
  }

  .cta-buttons {
    justify-content: flex-start;
  }

  .hero-stats {
    justify-content: flex-start;
  }

  .social-proof {
    text-align: left;
  }

  .company-logos {
    justify-content: flex-start;
  }

  .hero-title {
    font-size: 4rem;
  }

  .hero-subtitle {
    font-size: 1.75rem;
  }
}

@media (min-width: 1200px) {
  .hero-title {
    font-size: 4.5rem;
  }

  .image-container {
    width: 350px;
    height: 350px;
  }
}
</style>




