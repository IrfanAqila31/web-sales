# sales-web

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Vue (Official)](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Recommended Browser Setup

- Chromium-based browsers (Chrome, Edge, Brave, etc.):
  - [Vue.js devtools](https://chromewebstore.google.com/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)
  - [Turn on Custom Object Formatter in Chrome DevTools](http://bit.ly/object-formatters)
- Firefox:
  - [Vue.js devtools](https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/)
  - [Turn on Custom Object Formatter in Firefox DevTools](https://fxdx.dev/firefox-devtools-custom-object-formatters/)

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) to make the TypeScript language service aware of `.vue` types.

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```

---

## 📝 Dokumentasi `NavbarComponent.vue`

File ini adalah komponen navigasi (Navbar) yang dibangun menggunakan **Vue 3** (Composition API / `<script setup>`) dan **Tailwind CSS** untuk styling. Komponen ini dirancang agar **responsif**, sehingga tampilan akan menyesuaikan secara otomatis antara layar besar (Desktop) dan layar kecil (Mobile).

### 🧩 1. Bagian Script (`<script setup lang="ts">`)
Bagian ini mengatur logika dari komponen, seperti inisialisasi variabel dan *state*.

| Baris | Kode / Elemen | Penjelasan |
| :--- | :--- | :--- |
| **1** | `<script setup lang="ts">` | Mendefinisikan blok script dengan fitur `setup` bawaan Vue 3 dan menggunakan bahasa TypeScript (`lang="ts"`). |
| **2** | `import { ref } from 'vue'` | Mengimpor fungsi `ref` dari library Vue untuk membuat variabel reaktif. |
| **4** | `const isMobileMenuOpen = ref(false)` | Membuat variabel reaktif bernama `isMobileMenuOpen` dengan nilai awal `false`. Variabel ini melacak apakah menu navigasi mobile sedang terbuka atau tertutup. Jika nilainya berubah, antarmuka akan otomatis diperbarui. |

### 🎨 2. Bagian Template (`<template>`)
Bagian ini berisi kerangka HTML dan styling visual antarmuka (UI).

| Baris | Kode / Elemen | Penjelasan |
| :--- | :--- | :--- |
| **7** | `<template>` | Tag pembuka yang membungkus seluruh elemen HTML komponen. |
| **8** | `<header class="fixed top-4 ...">` | Wadah utama navbar. Class Tailwind membuatnya melayang (`fixed`) di posisi atas (`top-4`), membentang penuh (`w-full`), dan berada di lapisan teratas (`z-50`) agar tidak tertutup elemen lain. |
| **9-12** | `<nav class="bg-white/80 ...">` | Kotak navigasi aktual. Menggunakan background putih transparan dengan efek kaca/blur (`backdrop-blur-md`), sudut melengkung penuh seperti kapsul (`rounded-full`), dan efek bayangan (`shadow-lg`). |
| **13-15** | `<a>My Republik...</a>` | Teks logo aplikasi ("My Republik Indonesia"). Teks "Indonesia" dibungkus `<span>` untuk diberi warna merah (`text-red-600`). |
| **16-27** | `<div class="hidden md:flex ...">` | Wadah tautan menu **Desktop**. Disembunyikan di layar kecil (`hidden`) dan dimunculkan di layar medium ke atas (`md:flex`). Berisi tautan ke `#hero` dan `#tentang` dengan efek ubah warna saat disorot kursor (*hover*). |
| **29-33** | `<button class="md:hidden ...">` | Tombol hamburger menu **Mobile**. Hanya muncul di layar kecil (`md:hidden`). Memiliki *event listener* `@click` untuk membalikkan nilai `isMobileMenuOpen` saat diklik (buka/tutup menu). |
| **34-48** | `<svg v-if="!isMobileMenuOpen">` | Ikon **Garis Tiga (Hamburger)**. Ditampilkan jika menu mobile dalam keadaan tertutup (`v-if="!isMobileMenuOpen"`). |
| **50-64** | `<svg v-else>` | Ikon **Silang (X)**. Ditampilkan jika menu mobile dalam keadaan terbuka (`v-else`). |
| **67-70** | `<div v-show="isMobileMenuOpen">` | Wadah *dropdown* menu **Mobile**. Hanya di-render dan dimunculkan jika `isMobileMenuOpen` bernilai `true`. Posisinya diatur tepat di bawah kapsul navbar (`absolute top-17`). |
| **71-84** | `<a @click="...">` | Tautan menu di dalam *dropdown* mobile. Saat diklik, menu mobile akan otomatis tertutup (`isMobileMenuOpen = false`) agar tidak menghalangi konten. |
| **86-87** | `</header></template>` | Tag penutup elemen `<header>` dan `<template>`. |
