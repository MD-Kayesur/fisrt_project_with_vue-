<template>
  <main class="flex min-h-screen w-full items-center justify-center p-6 bg-[#1b1b1f]">
    <div class="w-full max-w-[480px] bg-[#202127] border border-white/10 rounded-2xl p-10 shadow-2xl text-center hover:border-emerald-500/30 transition-all duration-300 animate-fade-in">
      
      <!-- Logo Container -->
      <div class="mb-8  inline-flex items-center justify-center w-16 h-16 bg-white/[0.02] border border-white/5 rounded-2xl shadow-inner animate-float">
        <svg class="w-10 h-10 drop-shadow-[0_0_12px_rgba(66,184,131,0.3)]" viewBox="0 0 128 128">
          <path fill="#42b883" d="M78.8,10L64,35.4L49.2,10H0l64,110l64-110H78.8z"/>
          <path fill="#35495e" d="M78.8,10L64,35.4L49.2,10H25.6L64,76.5l38.4-66.5H78.8z"/>
        </svg>
      </div>

      <!-- Title -->
      <h1 class="text-3xl font-extrabold text-white mb-4 tracking-tight">
        Vue 3 + TypeScript
      </h1>

      <!-- Description -->
      <p class="text-slate-400 text-sm leading-relaxed mb-8  mx-auto">
        Welcome to your next-generation workspace. This setup features hot module replacement, reactive state, and strict type safety.
      </p>

      <!-- Button -->
      <div class="flex justify-center">
        <button 
          class="px-8 py-3 text-sm font-semibold text-white bg-emerald-500 hover:bg-emerald-600 rounded-xl shadow-lg shadow-emerald-500/20 hover:shadow-xl hover:shadow-emerald-500/30 active:scale-95 transition-all duration-200 cursor-pointer"
          @click="handleClick"
        >
          Click Me
        </button>
      </div>

      <!-- Reactive Message -->
      <transition name="slide-up">
        <div v-if="message" class="mt-6 p-4 bg-emerald-500/10 border border-emerald-500/20 rounded-xl flex items-center justify-center gap-2">
          <span class="text-emerald-400">✨</span>
          <p class="text-[13px] font-medium text-emerald-300 m-0">{{ message }}</p>
        </div>
      </transition>

    </div>
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
.animate-float {
  animation: float 4s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-8px);
  }
}

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
