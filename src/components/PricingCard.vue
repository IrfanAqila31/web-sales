<script setup lang="ts">
defineProps<{
  name: string
  speed: string
  description: string
  price: string
  features: string[]
  image: string
  imagePosition?: string
}>()
</script>
<template>
  <article
    class="flex flex-col p-8 h-full bg-white border border-slate-200 rounded-3xl shadow-sm hover:shadow-md transition-shadow duration-300"
  >
    <!-- nama paket dan kecepatan -->
    <header class="mb-3">
      <!-- membedakan posisi gambar pertama saja -->
      <img
        :src="image"
        :alt="name"
        width="400"
        height="160"
        loading="lazy"
        :class="['w-full h-40 object-cover rounded-xl mb-4', imagePosition || 'object-[50%_40%]']"
      />
      <h3 class="text-lg font-medium text-slate-900">{{ name }}</h3>
      <p class="text-4xl font-bold text-slate-900 mt-2">{{ speed }}</p>
      <p class="text-sm text-slate-500 mt-2">{{ description }}</p>
    </header>
    <div class="mb-6">
      <p class="flex items-baseline gap-1">
        <span class="text-3xl font-bold text-slate-900">{{ price }}</span>
        <span class="text-sm text-slate-600">/bulan</span>
      </p>
    </div>
    <ul class="flex-1 space-y-3 mb-8">
      <li v-for="feature in features" :key="feature" class="flex items-start gap-3">
        <svg
          class="w-5 h-5 text-indigo-600 shrink-0 mt-0.5"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="2"
          stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" d="M4.5 12.75l6 6 9-13.5" />
        </svg>
        <span class="text-slate-700">{{ feature }}</span>
      </li>
    </ul>
    <footer>
      <a
        href="#"
        class="flex justify-center items-center gap-3 w-full py-3 px-4 bg-linear-to-r from-violet-600 to-purple-600 shadow-sm hover:shadow-lg text-white text-center font-medium rounded-xl transition duration-300 hover:bg-linear-to-r hover:from-violet-500 hover:to-purple-500"
      >
        <svg
          aria-hidden="true"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
          class="w-5 h-5 fill-current"
        >
          <path
            d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"
          /></svg
        >Pesan Sekarang
      </a>
    </footer>
  </article>
</template>
