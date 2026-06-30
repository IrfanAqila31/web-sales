<script setup lang="ts">
const daftarWilayah = [
  'Mataram',
  'Lombok Tengah',
  'Lombok Barat',
  'Lombok Timur',
  'Lombok Utara',
  'Bima',
  'Dompu',
  'Sumbawa',
  'Sumbawa Barat',
  'Flores',
  'Kupang',
  'Sumba',
  'Timor Tengah Utara',
]
const daftarProses = [
  {
    title: 'Hubungi Sales',
    desc: 'Hubungi kami via WhatsApp atau telepon',
  },
  {
    title: 'Pilih Paket',
    desc: 'Pilih paket internet yang sesuai kebutuhan Anda',
  },
  {
    title: 'Survey Lokasi',
    desc: 'Kami survey lokasi untuk memastikan ketersediaan',
  },
  {
    title: 'Instalasi',
    desc: 'Teknisi kami melakukan instalasi di lokasi Anda',
  },
  {
    title: 'WiFi Aktif',
    desc: 'Internet siap digunakan, selamat menikmati!',
  },
]
</script>

<template>
  <section id="area-layanan" class="pt-26 pb-26">
    <div class="w-full max-w-7xl mx-auto">
      <div class="w-full px-4">
        <div class="max-w-xl mx-auto text-center mb-5">
          <h2 class="font-bold text-3xl mb-2">Area Layanan Kami</h2>
          <h3 class="font-bold text-xl md:text-2xl mb-2 text-violet-800">
            Kami Tersedia di Banyak Wilayah
          </h3>
          <p class="text-slate-600 font-medium text-sm md:text-base">
            Layanan internet kami sudah tersedia di berbagai area. Jika lokasi Anda belum ada
            dilist, hubungi untuk informasi lebih lanjut
          </p>
        </div>
        <figure class="flex justify-center mt-12 mb-16 relative">
          <img
            src="../assets/indonesia.svg"
            alt="Peta Area Layanan"
            width="896"
            height="400"
            loading="lazy"
            class="w-full max-w-4xl drop-shadow-xl hover:scale-105 transition-transform duration-500"
          />
          <figcaption class="sr-only">
            Peta jangkauan layanan internet kami di seluruh Indonesia
          </figcaption>
        </figure>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <article
            class="bg-blue-50/50 border border-blue-100 rounded-3xl p-8 flex flex-col h-full"
          >
            <header class="sr-only">
              <h3>Daftar Koya Wilayah</h3>
            </header>
            <ul
              class="grid grid-flow-col grid-rows-7 gap-x-5 gap-y-4 mb-8 flex-1 overflow-x-auto pb-2"
            >
              <li v-for="wilayah in daftarWilayah" :key="wilayah" class="flex items-center gap-3">
                <svg
                  class="w-5 h-5 text-blue-600 shrink-0"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="3"
                  stroke="currentColor"
                >
                  <path stroke-linecap="round" stroke-linejoin="round" d="M4.5 12.75l6 6 9-13.5" />
                </svg>
                <span class="text-slate-700 font-medium text-sm">{{ wilayah }}</span>
              </li>
            </ul>
            <footer>
              <a
                href="#"
                class="inline-flex justify-center items-center gap-2 w-full py-3 px-6 bg-linear-to-r from-violet-600 to-purple-600 text-white font-medium rounded-xl transition duration-300 shadow-sm hover:shadow-md"
              >
                <svg
                  aria-hidden="true"
                  viewBox="0 0 24 24"
                  xmlns="http://www.w3.org/2000/svg"
                  class="w-5 h-5 fill-current"
                >
                  <path
                    d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"
                  />
                </svg>
                Cek Ketersediaan
              </a>
            </footer>
          </article>
          <article
            class="bg-white border border-slate-200 shadow-sm rounded-3xl p-8 flex flex-col h-full"
          >
            <header class="mb-8">
              <h3 class="text-lg font-medium text-slate-500">Proses Pemasangan</h3>
              <p class="text-3xl font-bold text-slate-900 mt-1">Mudah & Cepat</p>
            </header>
            <ul class="space-y-6">
              <li
                v-for="(proses, index) in daftarProses"
                :key="proses.title"
                class="flex items-start gap-4"
              >
                <div
                  class="shrink-0 w-12 h-12 rounded-full bg-violet-600 flex items-center justify-center text-white font-bold text-lg shadow-md"
                >
                  {{ index + 1 }}
                </div>
                <div>
                  <h4 class="text-slate-900 font-bold text-lg">{{ proses.title }}</h4>
                  <p class="text-slate-600 text-sm mt-1 leading-relaxed">{{ proses.desc }}</p>
                </div>
              </li>
            </ul>
          </article>
        </div>
      </div>
    </div>
  </section>
</template>
