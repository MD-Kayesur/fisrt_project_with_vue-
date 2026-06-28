<template>
  <main class="home-container">
    <section class="glass-card hero-card animate-fade-in">
      <div class="logo-animation">
        <svg class="vue-logo" viewBox="0 0 128 128" width="80" height="80">
          <path fill="#42b883" d="M78.8,10L64,35.4L49.2,10H0l64,110l64-110H78.8z"/>
          <path fill="#35495e" d="M78.8,10L64,35.4L49.2,10H25.6L64,76.5l38.4-66.5H78.8z"/>
        </svg>
      </div>

      <h1 class="glow-text">{{ title }}</h1>

      <p class="description">{{ description }}</p>

      <div class="action-section">
        <button class="action-btn" @click="handleClick">
          <span>Click Me</span>
          <div class="btn-glow"></div>
        </button>
      </div>

      <transition name="slide-up">
        <div v-if="message" class="message-box">
          <span class="info-icon">✨</span>
          <p class="message">{{ message }}</p>
        </div>
      </transition>
    </section>
  </main>
</template>

<script setup lang="ts">
import { ref } from "vue";

const title = ref<string>("Vue 3 + TypeScript");

const description = ref<string>(
  "Welcome to your next-generation workspace. This setup features hot module replacement, reactive state, and strict type safety."
);

const message = ref<string>("");

const handleClick = (): void => {
  message.value = "Hello! You've successfully triggered a reactive state change.";
};
</script>

<style scoped>
.home-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: calc(100vh - 100px);
  padding: 20px;
}

.glass-card {
  background: rgba(255, 255, 255, 0.03);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 24px;
  padding: 50px 40px;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3);
  width: 100%;
  max-width: 580px;
  text-align: center;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
}

.hero-card:hover {
  border-color: rgba(66, 184, 131, 0.3);
  box-shadow: 0 20px 50px rgba(66, 184, 131, 0.1);
}

.logo-animation {
  margin-bottom: 24px;
  display: inline-block;
  animation: float 4s ease-in-out infinite;
}

.vue-logo {
  filter: drop-shadow(0 0 15px rgba(66, 184, 131, 0.4));
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-8px);
  }
}

.glow-text {
  font-size: 2.5rem;
  font-weight: 800;
  margin-bottom: 16px;
  background: linear-gradient(135deg, #42b883 0%, #35495e 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 2px 8px rgba(66, 184, 131, 0.2));
}

.description {
  color: #a0aec0;
  font-size: 1.05rem;
  line-height: 1.6;
  margin-bottom: 35px;
}

.action-section {
  display: flex;
  justify-content: center;
}

.action-btn {
  position: relative;
  padding: 14px 32px;
  font-size: 1rem;
  font-weight: 600;
  color: #ffffff;
  background: linear-gradient(135deg, #42b883 0%, #2bb876 100%);
  border: none;
  border-radius: 12px;
  cursor: pointer;
  overflow: hidden;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  box-shadow: 0 4px 15px rgba(66, 184, 131, 0.3);
}

.action-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(66, 184, 131, 0.5);
}

.action-btn:active {
  transform: translateY(1px);
}

.btn-glow {
  position: absolute;
  top: 0;
  left: -50%;
  width: 200%;
  height: 100%;
  background: linear-gradient(
    90deg,
    rgba(255, 255, 255, 0) 0%,
    rgba(255, 255, 255, 0.2) 50%,
    rgba(255, 255, 255, 0) 100%
  );
  transform: skewX(-20deg);
  transition: 0.75s;
}

.action-btn:hover .btn-glow {
  left: 120%;
}

.message-box {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  margin-top: 30px;
  padding: 16px;
  background: rgba(66, 184, 131, 0.1);
  border: 1px solid rgba(66, 184, 131, 0.2);
  border-radius: 12px;
}

.info-icon {
  font-size: 1.2rem;
}

.message {
  color: #e2e8f0;
  font-weight: 500;
  font-size: 0.95rem;
  margin: 0;
}

/* Animations */
.animate-fade-in {
  animation: fadeIn 0.8s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(15px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.slide-up-enter-active,
.slide-up-leave-active {
  transition: all 0.3s ease-out;
}

.slide-up-enter-from {
  opacity: 0;
  transform: translateY(10px);
}

.slide-up-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
