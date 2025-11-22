<template>
  <div
    :class="
      appStore.darkMode
        ? 'fit column wrap justify-center items-center content-center q-pb-xl element-dark'
        : 'fit column wrap justify-center items-center content-center q-pb-xl element'
    "
  >
    <div class="fit row justify-center">
      <h3
        class="mx-auto mb-4 max-w-4xl text-center text-3xl font-bold md:text-6xl text-bold"
      >
        Cómo Trabajamos
      </h3>
      <div class="q-px-xl">
        <p class="text-h6 text-center">
          En Apromed seguimos un riguroso proceso para asegurar la calidad y
          seguridad de los productos que entregamos. Aquí le mostramos un
          vistazo a nuestro método de trabajo:
        </p>
      </div>
    </div>

    <div class="fit row wrap justify-evenly items-center content-center">
      <div
        v-for="step in steps"
        :key="step.number"
        class="q-py-md"
      >
        <InfoCard
          :title="step.title"
          :content="step.content"
          :number="step.number"
          height="450px"
          width="270px"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useAuthStore } from '../../stores/auth';
import InfoCard from '../shared/InfoCard.vue';

const appStore = useAuthStore();

const steps = [
  {
    number: 1,
    title: 'Selección de Productos',
    content:
      'Seleccionamos los productos más adecuados de acuerdo a la demanda del mercado y los análisis clínicos, asegurando siempre la máxima calidad y efectividad.',
  },
  {
    number: 2,
    title: 'Control Riguroso',
    content:
      'Cada producto que llega a nuestras manos pasa por un estricto proceso de control de calidad y seguridad, garantizado por nuestras certificaciones de alto nivel.',
  },
  {
    number: 3,
    title: 'Distribución',
    content:
      'Operamos una red de distribución eficiente que garantiza que nuestros productos lleguen óptimamente a cada uno de nuestros clientes.',
  },
  {
    number: 4,
    title: 'Soporte Constante',
    content:
      'Ofrecemos soporte constante a nuestros clientes durante todo el proceso, desde la selección del producto hasta su entrega. Su satisfacción es nuestra prioridad.',
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
