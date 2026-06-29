<script setup lang="ts">
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)
</script>

<template>
  <header class="fixed top-4 left-0 w-full z-50 flex justify-center px-4">
    <nav
      aria-label="Navigasi Utama"
      class="bg-linear-to-bl from-violet-600/70 to-purple-600/70 backdrop-blur-sm border border-white/50 shadow-lg rounded-2xl w-full max-w-7xl px-6 py-3 md:py-5 flex items-center justify-between"
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
          href="#tentang"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >Paket Gamer</a
        >
        <a
          href="#tentang"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >Promo</a
        >
        <a
          href="#tentang"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >Cara Daftar</a
        >
        <a
          href="#tentang"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >FAQ</a
        >
        <a
          href="#tentang"
          class="text-sm font-bold text-slate-100 hover:text-violet-200 transition-colors"
          >Kontak</a
        >
      </div>

      <button
        @click="isMobileMenuOpen = !isMobileMenuOpen"
        class="lg:hidden text-slate-50 hover:text-slate-100 transition duration-500 focus:outline-none p-1"
        aria-label="Buka Menu Utama"
      >
        <svg
          v-if="!isMobileMenuOpen"
          xmlns="http://www.w3.org/2000/svg"
          class="h-7 w-7"
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
          class="h-7 w-7"
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
      </button>
    </nav>
    <div
      v-show="isMobileMenuOpen"
      class="absolute top-20 left-4 right-4 bg-linear-to-bl from-violet-600/70 to-purple-600/70 backdrop-blur-md rounded-2xl shadow-xl border border-slate-100 p-5 lg:hidden flex flex-col space-y-2"
    >
      <a
        @click="isMobileMenuOpen = false"
        href="#hero"
        class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg  transition-colors"
      >
        Beranda
      </a>
      <a
        @click="isMobileMenuOpen = false"
        href="#tentang"
        class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
      >
        Paket Internet
      </a>
      <a
        @click="isMobileMenuOpen = false"
        href="#tentang"
        class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
      >
        Paket Combo
      </a>
      <a
        @click="isMobileMenuOpen = false"
        href="#tentang"
        class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
      >
        Paket Gamer
      </a>
      <a
        @click="isMobileMenuOpen = false"
        href="#tentang"
        class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
      >
        Promo
      </a>
      <a
        @click="isMobileMenuOpen = false"
        href="#tentang"
        class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
      >
        Cara Daftar
      </a>
      <a
        @click="isMobileMenuOpen = false"
        href="#tentang"
        class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
      >
        FAQ
      </a>
      <a
        @click="isMobileMenuOpen = false"
        href="#tentang"
        class="text-base font-bold text-slate-50 hover:text-slate-100 p-3 rounded-lg transition-colors"
      >
        Kontak
      </a>
    </div>
  </header>
</template>
