<script setup lang="ts">
import NavbarComponent from './components/NavbarComponent.vue'
import HomeSection from './components/HomeSection.vue'
import PaketSection from './components/PaketSection.vue'
import AreaSection from './components/AreaSection.vue'
</script>

<template>
  <header>
    <NavbarComponent />
  </header>
  <main>
    <HomeSection />
    <PaketSection />
    <AreaSection />
  </main>
</template>

<style scoped></style>
