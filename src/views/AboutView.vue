<template>
  <div class="about-container">
    <div class="glass-card header-card animate-fade-in">
      <h1 class="glow-text">About This Application</h1>
      <p class="subtitle">
        A modern, reactive workspace built with Vue 3, TypeScript, and Vite.
      </p>
    </div>

    <div class="grid-layout">
      <div 
        v-for="(tech, index) in techStack" 
        :key="tech.name"
        class="glass-card tech-card"
        :style="{ animationDelay: `${(index + 1) * 150}ms` }"
      >
        <div class="tech-icon-wrapper" :style="{ background: tech.color }">
          <span class="tech-icon">{{ tech.icon }}</span>
        </div>
        <h3>{{ tech.name }}</h3>
        <p>{{ tech.description }}</p>
        <a :href="tech.link" target="_blank" rel="noopener" class="learn-more">
          Explore {{ tech.name }} →
        </a>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface TechItem {
  name: string
  description: string
  icon: string
  color: string
  link: string
}

const techStack = ref<TechItem[]>([
  {
    name: 'Vue 3',
    description: 'The Progressive JavaScript Framework utilizing the Composition API and high-performance virtual DOM.',
    icon: '💚',
    color: 'rgba(66, 184, 131, 0.15)',
    link: 'https://vuejs.org/'
  },
  {
    name: 'TypeScript',
    description: 'Strongly typed programming language that builds on JavaScript, giving you better tooling at any scale.',
    icon: '💙',
    color: 'rgba(49, 120, 198, 0.15)',
    link: 'https://www.typescriptlang.org/'
  },
  {
    name: 'Vite',
    description: 'Next-generation front-end tooling that is fast, lean, and features hot module replacement out-of-the-box.',
    icon: '⚡',
    color: 'rgba(255, 197, 23, 0.15)',
    link: 'https://vite.dev/'
  },
  {
    name: 'Pinia',
    description: 'The intuitive, type-safe, and flexible store library for Vue, facilitating clean state management.',
    icon: '🍍',
    color: 'rgba(254, 219, 58, 0.15)',
    link: 'https://pinia.vuejs.org/'
  }
])
</script>

<style scoped>
.about-container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 40px 20px;
  min-height: calc(100vh - 100px);
}

.glass-card {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 20px;
  padding: 30px;
  box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.2);
  transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
}

.header-card {
  text-align: center;
  margin-bottom: 40px;
  border: 1px solid rgba(66, 184, 131, 0.15);
}

.glow-text {
  font-size: 2.5rem;
  font-weight: 800;
  margin-bottom: 12px;
  background: linear-gradient(135deg, #42b883 0%, #35495e 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 2px 8px rgba(66, 184, 131, 0.2));
}

.subtitle {
  font-size: 1.1rem;
  color: #a0aec0;
}

.grid-layout {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 24px;
}

.tech-card {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  animation: fadeInUp 0.6s cubic-bezier(0.165, 0.84, 0.44, 1) both;
}

.tech-card:hover {
  transform: translateY(-8px);
  border-color: rgba(255, 255, 255, 0.2);
  box-shadow: 0 12px 40px 0 rgba(66, 184, 131, 0.15);
}

.tech-icon-wrapper {
  width: 48px;
  height: 48px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  margin-bottom: 20px;
}

.tech-card h3 {
  font-size: 1.3rem;
  color: #fff;
  margin-bottom: 10px;
  font-weight: 700;
}

.tech-card p {
  color: #a0aec0;
  font-size: 0.95rem;
  line-height: 1.5;
  margin-bottom: 20px;
  flex-grow: 1;
}

.learn-more {
  color: #42b883;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.9rem;
  transition: transform 0.2s ease;
}

.learn-more:hover {
  transform: translateX(4px);
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fadeIn 0.8s ease-out both;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
