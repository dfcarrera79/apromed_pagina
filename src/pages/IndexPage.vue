<template>
  <q-page>
    <q-page-container style="padding-top: 0px">
      <!-- Hero Section with Carousel -->
      <HeroCarousel />

      <!-- About Section: Quiénes Somos -->
      <AboutSection />

      <!-- Work Process Section: Cómo Trabajamos -->
      <WorkProcessSection />

      <!-- Features Section: Nos Destacamos -->
      <FeaturesSection />

      <!-- Contact Section: Contáctanos -->
      <ContactSection />

      <!-- Scroll to Top Button -->
      <ScrollToTop />

      <!-- WhatsApp Floating Button -->
      <WhatsAppButton phone-number="593988130131" />

      <!-- Footer -->
      <q-separator />
      <FootApromed />
    </q-page-container>
  </q-page>
</template>

<script setup lang="ts">
import FootApromed from '../components/FootApromed.vue';
import HeroCarousel from '../components/home/HeroCarousel.vue';
import AboutSection from '../components/home/AboutSection.vue';
import WorkProcessSection from '../components/home/WorkProcessSection.vue';
import FeaturesSection from '../components/home/FeaturesSection.vue';
import ContactSection from '../components/home/ContactSection.vue';
import ScrollToTop from '../components/shared/ScrollToTop.vue';
import WhatsAppButton from '../components/shared/WhatsAppButton.vue';
</script>

<style lang="scss" scoped>
// Global styles are now in individual components
</style>
