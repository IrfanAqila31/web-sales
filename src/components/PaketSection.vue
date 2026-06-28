<script setup lang="ts">
import PricingCard from './PricingCard.vue'

const daftarPaket = [
  {
    name: 'Basic',
    speed: '20 Mbps',
    description: 'Cocok Untuk Kebutuhan Dasar',
    price: 'Rp250.000',
    features: ['Unlimited Kuota', 'Wifi Router', 'Support 24/7', 'Internet Cepat'],
    image: '/img/paket-internet-1.jpeg',
    imagePosition: 'object-top',
  },
  {
    name: 'Family',
    speed: '100 Mbps',
    description: 'Cocok Untuk Keluarga',
    price: 'Rp450.000',
    features: [
      '20 users',
      '5GB of storage',
      'Email support',
      'Help center access',
      'Phone support',
      'Community access',
    ],
    image: '/img/paket-internet-2.jpeg',
  },
  {
    name: 'Bisnis',
    speed: '300 Mbps',
    description: 'Untuk Perusahaan & Bisnis',
    price: 'Rp900.000',
    features: [
      'Unlimited Kuota',
      'Wifi Router High End',
      'IP Public (Opsional)',
      'Support Prioritas 24/7',
      'Instalasi Cepat',
    ],
    image: '/img/paket-internet-3.jpeg',
  },
]
</script>

<template>
  <section class="pt-26 pb-26">
    <div class="w-full max-w-7xl mx-auto">
      <div class="w-full px-4">
        <div class="max-w-xl mx-auto text-center mb-5">
          <h2 class="font-bold text-3xl mb-2">Pilih Paket Internet Terbaik untuk Anda</h2>
          <p class="text-slate-600 font-medium text-sm md:text-base">
            Temukan paket internet yang sesuai dengan kebutuhan Anda dengan harga terjangkau.
          </p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 justify-center">
          <PricingCard
            v-for="paket in daftarPaket"
            :key="paket.name"
            :name="paket.name"
            :speed="paket.speed"
            :description="paket.description"
            :price="paket.price"
            :features="paket.features"
            :image="paket.image"
            :imagePosition="paket.imagePosition"
          />
        </div>
      </div>
    </div>
  </section>
</template>
