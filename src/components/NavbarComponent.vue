<script setup lang="ts">
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)
</script>

<template>
  <header class="fixed top-4 left-0 w-full z-50 flex justify-center px-4">
    <nav
      aria-label="Navigasi Utama"
      class="bg-linear-to-bl from-violet-600/70 to-purple-600/70 backdrop-blur-sm shadow-lg rounded-2xl w-full max-w-7xl px-6 py-3 md:py-5 flex items-center justify-between"
    >
      <a href="#" class="text-lg md:text-xl font-bold text-slate-900" aria-label="Logo Mahreen"
        >My Republik <span class="text-slate-50">Indonesia</span></a
      >
      <div class="hidden lg:flex items-center space-x-8">
        <a
          href="#home"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >Beranda</a
        >
        <a
          href="#paket-internet"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >Paket Internet</a
        >
        <a
          href="#area-layanan"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >Area Layanan</a
        >
        <a
          href="#promo"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >Promo</a
        >
        <a
          href="#faq"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >FAQ</a
        >

        <a
          href="#kontak"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >Kontak</a
        >
      </div>

      <button
        @click="isMobileMenuOpen = !isMobileMenuOpen"
        class="lg:hidden text-slate-50 hover:text-slate-100 focus:outline-none relative w-9 h-9 flex items-center justify-center"
        aria-label="Buka Menu Utama"
      >
        <Transition name="rotate-fade">
          <svg
            v-if="!isMobileMenuOpen"
            xmlns="http://www.w3.org/2000/svg"
            class="h-7 w-7 absolute"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
          <svg
            v-else
            xmlns="http://www.w3.org/2000/svg"
            class="h-7 w-7 absolute"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </Transition>
      </button>
    </nav>
    <transition name="slide-down">
      <div
        v-show="isMobileMenuOpen"
        class="absolute top-16 left-4 right-4 bg-linear-to-bl from-violet-600/70 to-purple-600/70 backdrop-blur-md rounded-2xl shadow-xl p-5 lg:hidden flex flex-col space-y-2"
      >
        <a
          @click="isMobileMenuOpen = false"
          href="#home"
          class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
        >
          Beranda
        </a>
        <a
          @click="isMobileMenuOpen = false"
          href="#paket-internet"
          class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
        >
          Paket Internet
        </a>
        <a
          @click="isMobileMenuOpen = false"
          href="#area-layanan"
          class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
        >
          Area Layanan
        </a>
        <a
          @click="isMobileMenuOpen = false"
          href="#promo"
          class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
        >
          Promo
        </a>
        <a
          @click="isMobileMenuOpen = false"
          href="#faq"
          class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
        >
          FAQ
        </a>
        <a
          @click="isMobileMenuOpen = false"
          href="#kontak"
          class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
        >
          Kontak
        </a>
      </div>
    </transition>
  </header>
</template>

<style scoped>
/* Animasi Transisi Hamburger ke Tanda Silang */
.rotate-fade-enter-active,
.rotate-fade-leave-active {
  transition: all 0.3s ease-in-out;
}
.rotate-fade-enter-from {
  opacity: 0;
  transform: rotate(-90deg) scale(0.5);
}
.rotate-fade-leave-to {
  opacity: 0;
  transform: rotate(90deg) scale(0.5);
}

/* Animasi Dropdown Menu HP (Meluncur dari atas) */
.slide-down-enter-active,
.slide-down-leave-active {
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}
.slide-down-enter-from,
.slide-down-leave-to {
  opacity: 0;
  transform: translateY(-20px) scaleY(0.95);
}
</style>
