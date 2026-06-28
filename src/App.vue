<template>
  <div class="min-h-screen flex flex-col">
    <header class="sticky top-0 z-[100] h-[64px] border-b border-[#2e2e32] bg-[#1a1a1a] flex items-center">
      <div class="max-w-[1200px] mx-auto px-6 w-full flex justify-between items-center">
        <!-- Left Section: Logo & Search -->
        <div class="flex items-center gap-4">
          <RouterLink to="/" class="flex items-center gap-2 hover:opacity-90 transition-opacity">
            <svg class="w-[24px] h-[24px]" viewBox="0 0 128 128">
               <path fill="#42b883" d="M78.8,10L64,35.4L49.2,10H0l64,110l64-110H78.8z"/>
              <path fill="#35495e" d="M78.8,10L64,35.4L49.2,10H25.6L64,76.5l38.4-66.5H78.8z"/>
            </svg>
            <span class="text-[15px] font-bold text-white tracking-tight">Vue.js</span>
          </RouterLink>
          
         
        </div>

        <!-- Right Section: Navigation Links -->
        <nav class="flex items-center gap-6 text-[13px] font-medium text-[#ebebeb]">
          <RouterLink 
            to="/" 
            class="transition-colors hover:text-[#42b883]" 
            active-class="text-[#42b883]"
          >
            Home
          </RouterLink>

          <RouterLink 
            to="/about" 
            class="transition-colors hover:text-[#42b883]" 
            active-class="text-[#42b883]"
          >
            About
          </RouterLink>
        </nav>
      </div>
    </header>

    <main class="flex-grow">
      <router-view v-slot="{ Component }">
        <transition name="fade-page" mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
    </main>

    <AppFooter />
  </div>
</template>

<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import AppFooter from './components/AppFooter.vue'
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&display=swap');
@import "tailwindcss";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Outfit', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  background-color: #1b1b1f;
  color: #f8fafc;
  min-height: 100vh;
  overflow-x: hidden;
  line-height: 1.5;
}
</style>

<style scoped>
/* Page Transitions */
.fade-page-enter-active,
.fade-page-leave-active {
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.fade-page-enter-from {
  opacity: 0;
  transform: translateY(10px);
}

.fade-page-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
