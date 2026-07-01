<script setup lang="ts">
import { ref } from 'vue'

const daftarPromo = [
  {
    id: 1,
    image: '/img/poster-promo.webp',
    alt: 'banner promo 1',
  },
  {
    id: 2,
    image: '/img/poster-promo.webp',
    alt: 'banner promo 2',
  },
  {
    id: 3,
    image: '/img/poster-promo.webp',
    alt: 'banner promo 3',
  },
]
const activeIndex = ref(0)

const onScroll = (e: Event) => {
  const target = e.target as HTMLElement
  const maxScroll = target.scrollWidth - target.clientWidth
  if (maxScroll <= 0) return

  const scrollPercentage = target.scrollLeft / maxScroll
  activeIndex.value = Math.round(scrollPercentage * (daftarPromo.length - 1))
}
</script>

<template>
  <section id="promo" class="pt-26 pb-26">
    <div class="w-full max-w-5xl mx-auto px-4">
      <div
        class="flex overflow-x-auto snap-x snap-mandatory gap-4 px-4 pb-8 hide-scrollbar"
        @scroll="onScroll"
      >
        <div
          v-for="promo in daftarPromo"
          :key="promo.id"
          class="shrink-0 w-full sm:w-[90%] md:w-[85%] rounded-3xl overflow-hidden shadow-md relative group snap-center"
        >
          <img
            :src="promo.image"
            :alt="promo.alt"
            width="1024"
            height="384"
            loading="lazy"
            class="w-full h-64 md:h-96 object-cover object-[50%_20%] group-hover:scale-105 transition-transform duration-700"
          />
        </div>
      </div>

      <!-- Indikator Titik (Dots) Modern -->
      <div class="flex justify-center items-center gap-2 mt-6">
        <div
          v-for="(promo, index) in daftarPromo"
          :key="'dot-' + promo.id"
          class="h-2 rounded-full transition-all duration-300"
          :class="activeIndex === index ? 'w-8 bg-violet-600' : 'w-2 bg-slate-300'"
        ></div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Menghilangkan garis abu-abu scrollbar (gulungan) */
.hide-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
.hide-scrollbar::-webkit-scrollbar {
  display: none;
}
</style>
