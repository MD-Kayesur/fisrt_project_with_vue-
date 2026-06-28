<template>
  <div class="app-layout">
    <header class="navbar glass-effect">
      <div class="nav-container">
        <div class="logo-section">
          <div class="logo-glow"></div>
          <span class="logo-icon">✨</span>
          <span class="logo-text">Workspace</span>
        </div>
        <nav class="nav-links">
          <RouterLink to="/" class="nav-item" active-class="active-link">Home</RouterLink>
          <RouterLink to="/about" class="nav-item" active-class="active-link">About</RouterLink>
        </nav>
      </div>
    </header>

    <main class="content-wrapper">
      <router-view v-slot="{ Component }">
        <transition name="fade-page" mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
    </main>
  </div>
</template>

<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Outfit', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  background: radial-gradient(circle at 30% 20%, #1e293b 0%, #0f172a 80%);
  color: #f8fafc;
  min-height: 100vh;
  overflow-x: hidden;
  line-height: 1.5;
}
</style>

<style scoped>
.app-layout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.navbar {
  position: sticky;
  top: 0;
  z-index: 100;
  padding: 20px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.glass-effect {
  background: rgba(15, 23, 42, 0.6);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
}

.nav-container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-section {
  position: relative;
  display: flex;
  align-items: center;
  gap: 10px;
}

.logo-glow {
  position: absolute;
  width: 32px;
  height: 32px;
  background: radial-gradient(circle, rgba(66, 184, 131, 0.4) 0%, rgba(66, 184, 131, 0) 70%);
  filter: blur(4px);
  left: -4px;
}

.logo-icon {
  font-size: 1.5rem;
  z-index: 1;
}

.logo-text {
  font-size: 1.3rem;
  font-weight: 800;
  background: linear-gradient(135deg, #fff 0%, #a0aec0 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  letter-spacing: -0.5px;
}

.nav-links {
  display: flex;
  gap: 10px;
  background: rgba(255, 255, 255, 0.03);
  padding: 6px;
  border-radius: 12px;
  border: 1px solid rgba(255, 255, 255, 0.05);
}

.nav-item {
  color: #94a3b8;
  text-decoration: none;
  font-size: 0.95rem;
  font-weight: 500;
  padding: 8px 18px;
  border-radius: 8px;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.nav-item:hover {
  color: #fff;
  background: rgba(255, 255, 255, 0.03);
}

.active-link {
  color: #fff;
  background: rgba(66, 184, 131, 0.15);
  box-shadow: inset 0 0 12px rgba(66, 184, 131, 0.1);
  border: 1px solid rgba(66, 184, 131, 0.15);
}

.content-wrapper {
  flex-grow: 1;
}

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
