<template>
  <div
    id="quienesSomos"
    :class="
      appStore.darkMode
        ? 'fit column wrap justify-center items-center content-center q-pb-xl element-dark'
        : 'fit column wrap justify-center items-center content-center q-pb-xl element'
    "
  >
    <div>
      <h3 class="text-center font-bold text-bold">Quiénes Somos</h3>
    </div>

    <div class="row justify-center items-center content-center">
      <div class="q-pa-md">
        <InfoCard
          title="Nuestra Misión"
          :content="misionContent"
          height="380px"
        />
      </div>

      <div class="q-pa-md">
        <InfoCard
          title="Nuestra Visión"
          :content="visionContent"
          height="380px"
        />
      </div>
    </div>

    <div class="row justify-center q-py-xl">
      <InfoCard
        title="Nuestro propósito"
        :content="propositoContent"
        width="370px"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { useAuthStore } from '../../stores/auth';
import InfoCard from '../shared/InfoCard.vue';

const appStore = useAuthStore();

const misionContent =
  'Distribuir productos farmacéuticos con un compromiso inquebrantable hacia la calidad, la seguridad laboral y la eficiencia. Nos esforzamos por mantener las condiciones óptimas de nuestros productos en beneficio de la salud y el bienestar de nuestros clientes.';

const visionContent =
  'Ser un referente en la distribución de productos farmacéuticos a nivel del austro y ampliar nuestro mercado a nivel nacional, siendo reconocida como una empresa comprometida con el fortalecimiento de sus procesos internos de control, cumplimiento legal y responsabilidad social.';

const propositoContent =
  'Mejorar la salud y el bienestar de las comunidades que servimos a través de una distribución farmacéutica de calidad y una dedicación apasionada hacia la salud y el bienestar de nuestros clientes.';
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
