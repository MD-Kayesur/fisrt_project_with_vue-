<template>
  <main
    class="min-h-screen bg-gradient-to-br from-[#111827] via-[#1e293b] to-[#0f172a] flex items-center justify-center p-6 overflow-hidden"
  >
    <!-- Background Blur -->
    <div
      class="absolute w-[500px] h-[500px] bg-emerald-500/20 rounded-full blur-[120px] top-[-100px] left-[-120px]"
    />

    <div
      class="absolute w-[450px] h-[450px] bg-cyan-500/20 rounded-full blur-[120px] bottom-[-100px] right-[-100px]"
    />

    <!-- Card -->
    <section
      class="relative z-10  w-full max-w-4xl rounded-3xl border border-white/10 bg-white/5 backdrop-blur-xl shadow-[0_0_60px_rgba(0,0,0,.35)] overflow-hidden"
    >
      <div class="p-6 sm:p-10 md:p-14">

        <!-- Logo -->
        <div
          class="w-24 h-24 rounded-3xl bg-white/5 border border-white/10 flex items-center justify-center mb-8 animate-float"
        >
          <svg width="70" viewBox="0 0 128 128">
            <path fill="#42b883"
              d="M78.8,10L64,35.4L49.2,10H0l64,110l64-110H78.8z" />
            <path fill="#35495e"
              d="M78.8,10L64,35.4L49.2,10H25.6L64,76.5l38.4-66.5H78.8z" />
          </svg>
        </div>

        <!-- Badge -->

        <div
          class="inline-flex px-4 py-2 rounded-full bg-emerald-500/10 border border-emerald-400/20 text-emerald-300 text-sm font-medium mb-6"
        >
          Vue 3 • TypeScript • TailwindCSS
        </div>

        <!-- Title -->

        <h1
          class="text-4xl sm:text-5xl md:text-6xl font-black text-white leading-tight tracking-tight"
        >
          Build Modern
          <span
            class="bg-gradient-to-r from-emerald-400 to-cyan-400 bg-clip-text text-transparent"
          >
            Vue Apps
          </span>
        </h1>

        <!-- Description -->

        <p
          class="mt-6 text-slate-300 text-lg leading-8 max-w-2xl"
        >
          A beautiful starter template powered by Vue 3,
          TypeScript, TailwindCSS and Vite. Fast, scalable,
          responsive and production ready.
        </p>

        <!-- Buttons -->

    <div class="mt-10 flex flex-wrap items-center justify-center gap-6">
  <!-- Primary Button -->
  <button
    @click="handleClick"
    type="button"
    class="inline-flex h-14 shrink-0 items-center justify-center gap-3 rounded-xl bg-gradient-to-r from-emerald-500 to-teal-500 px-8 text-base font-semibold text-white shadow-lg shadow-emerald-500/30 transition-all duration-300 hover:-translate-y-1 hover:scale-105 hover:from-emerald-400 hover:to-teal-400 hover:shadow-xl hover:shadow-emerald-500/40 active:scale-95"
  >
    <span class="text-xl leading-none">🚀</span>
    <span>Get Started</span>
  </button>

  <!-- Secondary Button -->
  <button
    type="button"
    class="inline-flex h-14 shrink-0 items-center justify-center gap-3 rounded-xl border border-white/10 bg-white/5 px-8 text-base font-semibold text-white backdrop-blur-md transition-all duration-300 hover:-translate-y-1 hover:bg-white/10 hover:shadow-lg active:scale-95"
  >
    <span class="text-xl leading-none">📖</span>
    <span>Documentation</span>
  </button>
</div>

        <!-- Feature Cards -->

        <div
          class="grid md:grid-cols-3 gap-6 mt-14"
        >

          <div
            class="p-6 rounded-2xl bg-white/5 border border-white/10 hover:border-emerald-400/30 transition hover:-translate-y-2"
          >
            <div class="text-3xl mb-4">⚡</div>

            <h3 class="text-white font-bold text-lg">
              Fast Development
            </h3>

            <p class="text-slate-400 mt-2">
              Hot Module Replacement with Vite.
            </p>

          </div>

          <div
            class="p-6 rounded-2xl bg-white/5 border border-white/10 hover:border-cyan-400/30 transition hover:-translate-y-2"
          >
            <div class="text-3xl mb-4">🛡</div>

            <h3 class="text-white font-bold text-lg">
              Type Safe
            </h3>

            <p class="text-slate-400 mt-2">
              Built with TypeScript support.
            </p>

          </div>

          <div
            class="p-6 rounded-2xl bg-white/5 border border-white/10 hover:border-purple-400/30 transition hover:-translate-y-2"
          >
            <div class="text-3xl mb-4">🚀</div>

            <h3 class="text-white font-bold text-lg">
              Production Ready
            </h3>

            <p class="text-slate-400 mt-2">
              Optimized for deployment.
            </p>

          </div>

        </div>

        <!-- Success Message -->

        <transition name="slide">
          <div
            v-if="message"
            class="mt-10 rounded-xl bg-emerald-500/10 border border-emerald-500/20 p-5 text-emerald-300"
          >
            ✨ {{ message }}
          </div>
        </transition>

      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
import { ref } from "vue";

const message = ref("");

const handleClick = () => {
  message.value =
    "Congratulations! Your Vue 3 application is working perfectly.";
};
</script>

<style scoped>
.animate-float {
  animation: float 5s ease-in-out infinite;
}

@keyframes float {
  50% {
    transform: translateY(-12px);
  }
}

.slide-enter-active,
.slide-leave-active {
  transition: all .35s;
}

.slide-enter-from,
.slide-leave-to {
  opacity: 0;
  transform: translateY(20px);
}
</style>