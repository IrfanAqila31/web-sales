<script setup lang="ts">
import NavbarComponent from './components/NavbarComponent.vue'
import HomeSection from './components/HomeSection.vue'
import PaketSection from './components/PaketSection.vue'
import AreaSection from './components/AreaSection.vue'
import PromoSection from './components/PromoSection.vue'
import FaqSection from './components/FaqSection.vue'
import KontakSection from './components/KontakSection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <header>
    <NavbarComponent />
  </header>
  <main>
    <HomeSection />
    <PaketSection />
    <AreaSection />
    <PromoSection />
    <FaqSection />
    <KontakSection />
  </main>
  <footer>
    <FooterSection />
  </footer>
</template>

<style scoped></style>
