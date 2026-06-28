<template>
  <main class="flex justify-center items-center min-h-[calc(100vh-100px)] p-5">
    <section class="bg-white/[0.03] backdrop-blur-[16px] border border-white/[0.08] rounded-[24px] py-[50px] px-10 shadow-[0_20px_50px_rgba(0,0,0,0.3)] w-full max-w-[580px] text-center transition-all duration-300 hover:border-[#42b883]/30 hover:shadow-[0_20px_50px_rgba(66,184,131,0.1)] animate-fade-in">
      <div class="mb-6 inline-block animate-float">
        <svg class="drop-shadow-[0_0_15px_rgba(66,184,131,0.4)]" viewBox="0 0 128 128" width="80" height="80">
          <path fill="#42b883" d="M78.8,10L64,35.4L49.2,10H0l64,110l64-110H78.8z"/>
          <path fill="#35495e" d="M78.8,10L64,35.4L49.2,10H25.6L64,76.5l38.4-66.5H78.8z"/>
        </svg>
      </div>

      <h1 class="text-[2.5rem] font-extrabold mb-4 bg-gradient-to-br from-[#42b883] to-[#35495e] bg-clip-text text-transparent drop-shadow-[0_2px_8px_rgba(66,184,131,0.2)]">{{ title }}</h1>

      <p class="text-[#a0aec0] text-[1.05rem] leading-[1.6] mb-[35px]">{{ description }}</p>

      <div class="flex justify-center">
        <button class="group relative py-[14px] px-8 text-base font-semibold text-white bg-gradient-to-br from-[#42b883] to-[#2bb876] rounded-xl overflow-hidden transition-all duration-200 shadow-[0_4px_15px_rgba(66,184,131,0.3)] hover:-translate-y-0.5 hover:shadow-[0_6px_20px_rgba(66,184,131,0.5)] active:translate-y-[1px] cursor-pointer" @click="handleClick">
          <span class="relative z-10">Click Me</span>
          <div class="absolute top-0 -left-[50%] w-[200%] h-full bg-gradient-to-r from-transparent via-white/20 to-transparent -skew-x-[20deg] transition-all duration-750 group-hover:left-[120%]"></div>
        </button>
      </div>

      <transition name="slide-up">
        <div v-if="message" class="flex items-center justify-center gap-3 mt-[30px] p-4 bg-[#42b883]/10 border border-[#42b883]/20 rounded-xl">
          <span class="text-[1.2rem]">✨</span>
          <p class="text-[#e2e8f0] font-medium text-[0.95rem] m-0">{{ message }}</p>
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
