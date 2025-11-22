<template>
  <div
    :class="
      appStore.darkMode
        ? 'fit column wrap justify-center items-center content-center q-pb-xl element-dark'
        : 'fit column wrap justify-center items-center content-center q-pb-xl element'
    "
    style="background-color: #bcbdc0; height: 600px"
  >
    <div class="fit column justify-center">
      <h3
        class="mx-auto mb-4 max-w-4xl text-center text-3xl font-bold md:text-6xl text-bold"
      >
        Nos Destacamos
      </h3>
      <div class="q-px-xl">
        <p class="text-h6 text-center">
          En Apromed, nos enorgullece ofrecer productos y servicios que destacan
          en la industria farmacéutica. Aquí algunos de ellos:
        </p>
      </div>
    </div>

    <div class="fit row wrap justify-evenly items-center content-center">
      <div v-for="feature in features" :key="feature.icon" class="q-py-md">
        <InfoCard
          :title="feature.title"
          :content="feature.content"
          :icon="feature.icon"
          height="588px"
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

const features = [
  {
    icon: 'security',
    title: 'Seguridad Garantizada',
    content:
      'Con Apromed, puede estar seguro de que todos nuestros productos cumplen con los más altos estándares de seguridad. Nuestro control de calidad estricto y riguroso asegura que cada producto que ofrecemos es seguro y efectivo para su uso.',
  },
  {
    icon: 'rocket_launch',
    title: 'Entrega Rápida y Eficiente',
    content:
      'Operamos una red de distribución rápida y eficiente para asegurar que los productos farmacéuticos que necesita lleguen a tiempo y en la mejor condición posible. Este nivel de eficiencia nos permite satisfacer las necesidades de nuestros clientes.',
  },
  {
    icon: 'support_agent',
    title: 'Soporte al Cliente',
    content:
      'Nuestro equipo de servicio al cliente está disponible para ayudarlo en cada etapa del proceso. Ya sea que tenga preguntas sobre nuestros productos, necesite ayuda con su pedido o tenga cualquier otra consulta, nuestro equipo dedicado está listo para ayudarlo.',
  },
];
</script>

<style lang="scss" scoped>
.element-dark {
  background: linear-gradient(
    142deg,
    #1a1a2e 0%,
    #003d7a 50%,
    #0f0f1e 100%
  ) !important;
}

.element {
  background: linear-gradient(
    142deg,
    #fff4e6 0%,
    #f5f7fa 50%,
    #f0f7ff 100%
  ) !important;
}
</style>
