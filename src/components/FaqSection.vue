<script setup lang="ts">
import { ref } from 'vue'
import FaqCard from './FaqCard.vue'

const faqs = [
  {
    question: 'Berapa lama proses pemasangan internet?',
    answer:
      'Proses pemasangan biasanya memakan waktu 1-3 hari kerja setelah Anda memilih paket dan kami mengonfirmasi ketersediaan di lokasi Anda.',
  },
  {
    question: 'Apakah ada biaya tambahan untuk instalasi?',
    answer:
      'Biaya instalasi bervariasi. Saat ini kami memberikan penawaran instalasi khusus untuk pengguna baru!',
  },
  {
    question: 'Bagaimana jika internet mengalami gangguan?',
    answer:
      'Kami memiliki tim dukungan teknis. Anda cukup menghubungi kami via WhatsApp dan teknisi kami akan segera melakukan pengecekan atau datang ke lokasi.',
  },
  {
    question: 'Apakah kuota internetnya benar-benar unlimited?',
    answer: 'Ya, semua paket internet kami bersifat Unlimited tanpa batasan kuota (FUP).',
  },
]

const activeIndex = ref<number | null>(null)

const toggleFaq = (index: number) => {
  activeIndex.value = activeIndex.value === index ? null : index
}
</script>

<template>
  <section id="faq" class="pt-26 pb-26 bg-slate-50">
    <div class="w-full max-w-5xl mx-auto px-4">
      <div class="text-center mb-12">
        <h2 class="font-bold text-3xl md:text-4xl text-slate-800 mb-4">
          Pertanyaan yang Sering Diajukan
        </h2>
        <p class="text-slate-600 font-medium">
          Temukan jawaban untuk pertanyaan umum seputar layanan kami.
        </p>
      </div>
      <div class="space-y-4">
        <FaqCard
          v-for="(faq, index) in faqs"
          :key="index"
          :question="faq.question"
          :answer="faq.answer"
          :isOpen="activeIndex === index"
          @toggle="toggleFaq(index)"
        />
      </div>
    </div>
  </section>
</template>
