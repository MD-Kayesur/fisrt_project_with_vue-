<template>
  <div class="max-w-[1000px] mx-auto px-5 py-10 min-h-[calc(100vh-129px)]">
    <div class="bg-white/5 backdrop-blur-[12px] border border-white/10 rounded-[20px] p-[30px] shadow-[0_8px_32px_0_rgba(0,0,0,0.2)] transition-all duration-[400ms] ease-[cubic-bezier(0.165,0.84,0.44,1)] text-center mb-10 border-[#42b883]/15 animate-fade-in">
      <h1 class="text-[2.5rem] font-extrabold mb-3 bg-gradient-to-br from-[#42b883] to-[#35495e] bg-clip-text text-transparent drop-shadow-[0_2px_8px_rgba(66,184,131,0.2)]">About This Application</h1>
      <p class="text-[1.1rem] text-[#a0aec0]">
        A modern, reactive workspace built with Vue 3, TypeScript, and Vite.
      </p>
    </div>

    <div class="grid grid-cols-[repeat(auto-fit,minmax(220px,1fr))] gap-6">
      <div 
        v-for="(tech, index) in techStack" 
        :key="tech.name"
        class="bg-white/5 backdrop-blur-[12px] border border-white/10 rounded-[20px] p-[30px] shadow-[0_8px_32px_0_rgba(0,0,0,0.2)] transition-all duration-[400ms] ease-[cubic-bezier(0.165,0.84,0.44,1)] flex flex-col items-start animate-fade-in-up hover:-translate-y-2 hover:border-white/20 hover:shadow-[0_12px_40px_0_rgba(66,184,131,0.15)]"
        :style="{ animationDelay: `${(index + 1) * 150}ms` }"
      >
        <div class="w-12 h-12 rounded-xl flex items-center justify-center text-[1.5rem] mb-5" :style="{ background: tech.color }">
          <span>{{ tech.icon }}</span>
        </div>
        <h3 class="text-[1.3rem] text-white mb-2.5 font-bold">{{ tech.name }}</h3>
        <p class="text-[#a0aec0] text-[0.95rem] leading-[1.5] mb-5 grow">{{ tech.description }}</p>
        <a :href="tech.link" target="_blank" rel="noopener" class="text-[#42b883] no-underline font-semibold text-[0.9rem] transition-transform duration-200 ease-out hover:translate-x-1">
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

.animate-fade-in-up {
  animation: fadeInUp 0.6s cubic-bezier(0.165, 0.84, 0.44, 1) both;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.animate-fade-in {
  animation: fadeIn 0.8s ease-out both;
}
</style>
