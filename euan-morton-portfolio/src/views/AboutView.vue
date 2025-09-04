<script setup>
import { personalInfo, education, certifications, otherActivities } from '@/data/portfolioData'
</script>

<template>
  <div class="about">
    <div class="container">
      <header class="page-header">
        <h1>About {{ personalInfo.name.split(' ')[0] }}</h1>
        <p class="page-subtitle">Get to know more about my background and experience</p>
      </header>

      <div class="about-content">
        <div class="profile-section">
          <div class="profile-image">
            <div class="image-placeholder">
              <svg width="80" height="80" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 12C14.7614 12 17 9.76142 17 7C17 4.23858 14.7614 2 12 2C9.23858 2 7 4.23858 7 7C7 9.76142 9.23858 12 12 12Z" fill="currentColor"/>
                <path d="M12 14C7.58172 14 4 17.5817 4 22H20C20 17.5817 16.4183 14 12 14Z" fill="currentColor"/>
              </svg>
            </div>
          </div>

          <div class="bio-summary">
            <h2>Professional Summary</h2>
            <div class="summary">
              <p v-for="(paragraph, index) in personalInfo.summary" :key="index">
                {{ paragraph }}
              </p>
            </div>
          </div>
        </div>

        <div class="info-grid">
          <div class="info-card">
            <h2>Education</h2>
            <ul class="education-list">
              <li v-for="(edu, index) in education" :key="index" class="education-item">
                <div class="degree">{{ edu.degree }}</div>
                <div class="institution">{{ edu.institution }}</div>
                <div class="location">{{ edu.location }}</div>
              </li>
            </ul>
          </div>

          <div class="info-card">
            <h2>Certifications</h2>
            <ul class="certification-list">
              <li v-for="(cert, index) in certifications" :key="index" class="certification-item">
                <div class="cert-title">{{ cert.title }}</div>
                <div class="cert-org">{{ cert.organization }}</div>
                <div class="cert-period">{{ cert.period }}</div>
              </li>
            </ul>
          </div>

          <div class="info-card">
            <h2>Other Activities</h2>
            <ul class="activities-list">
              <li v-for="(activity, index) in otherActivities" :key="index" class="activity-item">
                <div class="activity-name">{{ activity.activity }}</div>
                <div class="activity-role">{{ activity.role }}</div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about {
  padding: 2rem 0;
  min-height: calc(100vh - 120px);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

.page-header {
  text-align: center;
  margin-bottom: 3rem;
}

.page-header h1 {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--color-heading);
  margin-bottom: 0.5rem;
}

.page-subtitle {
  font-size: 1.2rem;
  color: var(--color-text);
  opacity: 0.8;
  margin: 0;
}

.about-content {
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

.profile-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
  background: var(--color-background-soft);
  padding: 2.5rem;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.profile-image {
  flex-shrink: 0;
}

.image-placeholder {
  width: 150px;
  height: 150px;
  background: var(--color-background-mute);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-text);
  opacity: 0.6;
  border: 3px solid hsla(160, 100%, 37%, 0.2);
}

.bio-summary {
  flex: 1;
  text-align: center;
}

.bio-summary h2 {
  font-size: 1.8rem;
  font-weight: 600;
  color: var(--color-heading);
  margin-bottom: 1.5rem;
}

.summary p {
  font-size: 1.1rem;
  line-height: 1.7;
  color: var(--color-text);
  margin-bottom: 1rem;
}

.summary p:last-child {
  margin-bottom: 0;
}

.info-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

.info-card {
  background: var(--color-background-soft);
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  border: 1px solid var(--color-border);
}

.info-card h2 {
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--color-heading);
  margin-bottom: 1.5rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid hsla(160, 100%, 37%, 0.3);
}

.info-card ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.info-card li {
  margin-bottom: 1.5rem;
  padding-bottom: 1.5rem;
  border-bottom: 1px solid var(--color-border);
}

.info-card li:last-child {
  margin-bottom: 0;
  padding-bottom: 0;
  border-bottom: none;
}

/* Education specific styles */
.education-item .degree {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--color-heading);
  margin-bottom: 0.25rem;
}

.education-item .institution {
  font-size: 1rem;
  color: var(--color-text);
  margin-bottom: 0.25rem;
}

.education-item .location {
  font-size: 0.9rem;
  color: var(--color-text);
  opacity: 0.7;
}

/* Certification specific styles */
.certification-item .cert-title {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--color-heading);
  margin-bottom: 0.25rem;
}

.certification-item .cert-org {
  font-size: 1rem;
  color: var(--color-text);
  margin-bottom: 0.25rem;
}

.certification-item .cert-period {
  font-size: 0.9rem;
  color: hsla(160, 100%, 37%, 1);
  font-weight: 500;
}

/* Activity specific styles */
.activity-item .activity-name {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--color-heading);
  margin-bottom: 0.25rem;
}

.activity-item .activity-role {
  font-size: 1rem;
  color: var(--color-text);
  opacity: 0.8;
}

@media (min-width: 768px) {
  .profile-section {
    flex-direction: row;
    text-align: left;
  }

  .bio-summary {
    text-align: left;
  }

  .info-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .page-header h1 {
    font-size: 3rem;
  }

  .info-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>


