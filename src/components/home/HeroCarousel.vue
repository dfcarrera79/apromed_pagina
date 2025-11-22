<template>
  <div
    :class="
      appStore.darkMode ? 'q-pa-none element-dark' : 'q-pa-none element'
    "
  >
    <div class="row justify-center q-py-sm">
      <img
        src="https://res.cloudinary.com/dvy167slj/image/upload/f_auto,q_auto/v1/apromed/logo_apromed"
        style="height: 150px"
      />
    </div>

    <q-carousel
      swipeable
      animated
      arrows
      :class="
        appStore.darkMode
          ? 'q-pa-none q-ma-none element-dark'
          : 'q-pa-none q-ma-none element'
      "
      :autoplay="autoplay"
      v-model="slide"
      v-model:fullscreen="fullscreen"
      infinite
      style="height: 480px; max-width: 920px; margin: 0 auto"
    >
      <q-carousel-slide
        v-for="(slideData, index) in slides"
        :key="index"
        :name="index + 1"
      >
        <q-img
          :src="slideData.image"
          height="400px"
          class="rounded-borders"
        />
        <div class="q-mt-md text-center">
          <p class="text-body1">
            <strong>{{ slideData.text }}</strong>
          </p>
        </div>
      </q-carousel-slide>
    </q-carousel>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { useAuthStore } from '../../stores/auth';

interface Slide {
  image: string;
  text: string;
}

const appStore = useAuthStore();
const slide = ref(1);
const autoplay = ref(true);
const fullscreen = ref(false);

const slides: Slide[] = [
  {
    image:
      'https://res.cloudinary.com/dvy167slj/image/upload/f_auto,q_auto/v1/apromed/img1.webp',
    text: 'Tu salud, nuestra prioridad.',
  },
  {
    image:
      'https://res.cloudinary.com/dvy167slj/image/upload/f_auto,q_auto/v1/apromed/img2.webp',
    text: 'Cuidando vidas, distribuyendo esperanza',
  },
  {
    image:
      'https://res.cloudinary.com/dvy167slj/image/upload/f_auto,q_auto/v1/apromed/img3',
    text: 'Juntos hacia un futuro más saludable',
  },
];
</script>

<style lang="scss" scoped>
.element-dark {
  background-image: linear-gradient(
    142deg,
    #5b5b5b 0%,
    rgba(0, 0, 0, 0.9) 100%
  ) !important;
}

.element {
  background-image: linear-gradient(
    142deg,
    #a4a4a4 0%,
    rgba(255, 255, 255, 0.9) 100%
  ) !important;
}
</style>
