<script setup>
import { personalInfo, education, certifications, otherActivities } from '@/data/portfolioData'
</script>

<template>
  <div class="about">
    <div class="container">
      <h1>About {{ personalInfo.name.split(' ')[0] }}</h1>
      
      <div class="about-content">
        <div class="profile-image">
          <!-- Replace with Euan's actual image -->
          <div class="image-placeholder">Photo</div>
        </div>
        
        <div class="bio">
          <div class="summary">
            <p v-for="(paragraph, index) in personalInfo.summary" :key="index">
              {{ paragraph }}
            </p>
          </div>
          
          <h2>Education</h2>
          <ul class="education-list">
            <li v-for="(edu, index) in education" :key="index">
              <strong>{{ edu.degree }}</strong> - {{ edu.institution }}, {{ edu.location }}
            </li>
          </ul>
          
          <h2>Certifications</h2>
          <ul class="certification-list">
            <li v-for="(cert, index) in certifications" :key="index">
              <strong>{{ cert.title }}</strong> - {{ cert.organization }} ({{ cert.period }})
            </li>
          </ul>
          
          <h2>Other Activities</h2>
          <ul class="activities-list">
            <li v-for="(activity, index) in otherActivities" :key="index">
              <strong>{{ activity.activity }}</strong> - {{ activity.role }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Styles remain the same */
</style>


