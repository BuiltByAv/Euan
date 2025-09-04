<script setup>
import { ref } from 'vue'
import { contactInfo, personalInfo } from '@/data/portfolioData'

const name = ref('')
const email = ref('')
const message = ref('')
const submitted = ref(false)
const loading = ref(false)

const submitForm = () => {
  loading.value = true
  
  // Simulate form submission
  setTimeout(() => {
    loading.value = false
    submitted.value = true
    
    // Reset form
    name.value = ''
    email.value = ''
    message.value = ''
    
    // Reset submitted status after 5 seconds
    setTimeout(() => {
      submitted.value = false
    }, 5000)
  }, 1000)
}
</script>

<template>
  <div class="contact">
    <div class="container">
      <h1>Get in Touch</h1>
      
      <div class="contact-content">
        <div class="contact-info">
          <h2>Contact Information</h2>
          
          <div class="info-item">
            <strong>Email:</strong>
            <a :href="`mailto:${contactInfo.email}`">{{ contactInfo.email }}</a>
          </div>
          
          <div class="info-item">
            <strong>LinkedIn:</strong>
            <a :href="contactInfo.linkedin" target="_blank">{{ contactInfo.linkedin }}</a>
          </div>
          
          <div class="info-item">
            <strong>Location:</strong>
            <span>{{ contactInfo.location }}</span>
          </div>
          
          <div class="info-item">
            <strong>Phone:</strong>
            <span>{{ personalInfo.phone }}</span>
          </div>
          
          <div class="availability">
            <h3>Current Availability</h3>
            <p>{{ contactInfo.availability }}</p>
          </div>
        </div>
        
        <div class="contact-form">
          <h2>Send a Message</h2>
          
          <form @submit.prevent="submitForm">
            <div class="form-group">
              <label for="name">Name</label>
              <input 
                type="text" 
                id="name" 
                v-model="name" 
                required
                placeholder="Your name"
              >
            </div>
            
            <div class="form-group">
              <label for="email">Email</label>
              <input 
                type="email" 
                id="email" 
                v-model="email" 
                required
                placeholder="Your email address"
              >
            </div>
            
            <div class="form-group">
              <label for="message">Message</label>
              <textarea 
                id="message" 
                v-model="message" 
                required
                placeholder="How can I help you?"
                rows="5"
              ></textarea>
            </div>
            
            <button 
              type="submit" 
              class="submit-button"
              :disabled="loading"
            >
              {{ loading ? 'Sending...' : 'Send Message' }}
            </button>
            
            <div v-if="submitted" class="success-message">
              Thank you for your message! I'll get back to you soon.
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.contact {
  padding: 2rem 0;
}

.container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 1rem;
}

h1 {
  margin-bottom: 2rem;
  text-align: center;
}

.contact-content {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.contact-info, .contact-form {
  background-color: var(--color-background-soft);
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

h2 {
  margin-top: 0;
  margin-bottom: 1.5rem;
  font-size: 1.5rem;
  color: hsla(160, 100%, 37%, 1);
}

.info-item {
  margin-bottom: 1rem;
  line-height: 1.6;
}

.info-item a {
  display: block;
  margin-top: 0.25rem;
}

.availability {
  margin-top: 2rem;
}

h3 {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 500;
}

input, textarea {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid var(--color-border);
  border-radius: 4px;
  background-color: var(--color-background);
  font-family: inherit;
  font-size: 1rem;
}

input:focus, textarea:focus {
  outline: none;
  border-color: hsla(160, 100%, 37%, 1);
}

.submit-button {
  background-color: hsla(160, 100%, 37%, 1);
  color: white;
  border: none;
  border-radius: 4px;
  padding: 0.75rem 1.5rem;
  font-size: 1rem;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.3s;
}

.submit-button:hover {
  background-color: hsla(160, 100%, 37%, 0.8);
}

.submit-button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}

.success-message {
  margin-top: 1rem;
  padding: 0.75rem;
  background-color: rgba(0, 200, 83, 0.1);
  border-left: 4px solid rgba(0, 200, 83, 1);
  border-radius: 4px;
}

@media (min-width: 768px) {
  .contact-content {
    flex-direction: row;
  }
  
  .contact-info {
    flex: 1;
  }
  
  .contact-form {
    flex: 2;
  }
}
</style>


