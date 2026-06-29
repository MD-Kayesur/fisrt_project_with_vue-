<template>
  <main
    class="min-h-screen bg-slate-950 flex items-center justify-center px-6 py-20"
  >
    <section
      class="w-full max-w-5xl rounded-3xl border border-white/10 bg-white/5 backdrop-blur-xl p-12"
    >
      <!-- Hero -->
      <div class="text-center">
        <div
          class="mx-auto mb-8 flex h-24 w-24 items-center justify-center rounded-3xl bg-white/5 border border-white/10"
        >
          🚀
        </div>

        <span
          class="inline-flex rounded-full border border-emerald-500/20 bg-emerald-500/10 px-4 py-2 text-sm font-medium text-emerald-300"
        >
          Vue 3 • TypeScript • Tailwind CSS
        </span>

        <h1 class="mt-8 text-5xl font-bold text-white">
          Build Modern Vue Applications
        </h1>

        <p class="mx-auto mt-6 max-w-2xl text-lg leading-8 text-slate-400">
          Create beautiful, responsive and production-ready applications using
          Vue 3, TypeScript, Vite and Tailwind CSS.
        </p>
      </div>

      <!-- Buttons -->
      <div class="mt-12 flex flex-wrap justify-center gap-6">
        <button
          @click="handleClick"
          class="inline-flex h-14 items-center justify-center gap-3 rounded-xl bg-emerald-500 px-8 text-base font-semibold text-white transition-all duration-300 hover:-translate-y-1 hover:bg-emerald-400 hover:shadow-lg hover:shadow-emerald-500/30 active:scale-95"
        >
          <span class="text-xl">🚀</span>
          <span>Get Started</span>
        </button>

        <button
          class="inline-flex h-14 items-center justify-center gap-3 rounded-xl border border-white/10 bg-white/5 px-8 text-base font-semibold text-white transition-all duration-300 hover:-translate-y-1 hover:bg-white/10 active:scale-95"
        >
          <span class="text-xl">📖</span>
          <span>Documentation</span>
        </button>
      </div>

      <!-- Features -->
      <div class="mt-20 grid gap-6 md:grid-cols-3">
        <div
          class="rounded-2xl border border-white/10 bg-white/5 p-8 transition hover:-translate-y-2 hover:border-emerald-500/30"
        >
          <div class="mb-5 text-4xl">⚡</div>
          <h3 class="text-xl font-semibold text-white">Fast Development</h3>
          <p class="mt-3 text-slate-400">
            Lightning-fast development powered by Vite.
          </p>
        </div>

        <div
          class="rounded-2xl border border-white/10 bg-white/5 p-8 transition hover:-translate-y-2 hover:border-cyan-500/30"
        >
          <div class="mb-5 text-4xl">🛡️</div>
          <h3 class="text-xl font-semibold text-white">Type Safe</h3>
          <p class="mt-3 text-slate-400">
            Full TypeScript support for safer code.
          </p>
        </div>

        <div
          class="rounded-2xl border border-white/10 bg-white/5 p-8 transition hover:-translate-y-2 hover:border-purple-500/30"
        >
          <div class="mb-5 text-4xl">🚀</div>
          <h3 class="text-xl font-semibold text-white">Production Ready</h3>
          <p class="mt-3 text-slate-400">
            Optimized for deployment and scalability.
          </p>
        </div>
      </div>

      <!-- Message -->
      <div
        v-if="message"
        class="mx-auto mt-16 max-w-2xl rounded-2xl border border-emerald-500/20 bg-emerald-500/10 p-5 text-center text-emerald-300"
      >
        ✨ {{ message }}
      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
import { ref } from "vue";

const message = ref("");

const handleClick = () => {
  message.value = "Congratulations! Your Vue application is working perfectly.";
};
</script>