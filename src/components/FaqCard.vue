<script setup lang="ts">
defineProps<{
  question: string
  answer: string
  isOpen: boolean
}>()
defineEmits<{
  (e: 'toggle'): void
}>()
</script>
<template>
  <article
    class="bg-white border border-slate-200 rounded-2xl overflow-hidden transition-shadow duration-300 shadow-sm hover:shadow-md"
  >
    <button
      @click="$emit('toggle')"
      class="flex items-center justify-between w-full p-6 text-left focus:outline-none cursor-pointer"
    >
      <h3 class="font-bold text-lg text-slate-800 pr-4">{{ question }}</h3>
      <svg
        class="w-6 h-6 shrink-0 transition-transform duration-300"
        :class="isOpen ? 'text-violet-600 rotate-180' : 'text-slate-400'"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
        stroke-width="2"
      >
        <path v-if="!isOpen" stroke-linecap="round" stroke-linejoin="round" d="M12 4v16m8-8H4" />
        <path v-else stroke-linecap="round" stroke-linejoin="round" d="M20 12H4" />
      </svg>
    </button>
    <div
      class="grid transition-all duration-300 ease-in-out"
      :class="isOpen ? 'grid-rows-[1fr] opacity-100' : 'grid-rows-[0fr] opacity-0'"
    >
      <div class="overflow-hidden">
        <div class="px-6 pb-6 text-slate-600 leading-relaxed">
          <p>{{ answer }}</p>
        </div>
      </div>
    </div>
  </article>
</template>
