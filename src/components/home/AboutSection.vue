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
          height="390px"
        />
      </div>

      <div class="q-pa-md">
        <InfoCard
          title="Nuestra Visión"
          :content="visionContent"
          height="390px"
        />
      </div>
    </div>

    <div class="row justify-center q-py-xl">
      <InfoCard
        title="Nuestro propósito"
        :content="propositoContent"
        width="390px"
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
  background: linear-gradient(
    142deg,
    #003d7a 0%,
    #1a1a2e 50%,
    #0f0f1e 100%
  ) !important;
  position: relative;

  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: radial-gradient(
      circle at 20% 50%,
      rgba(255, 153, 27, 0.1) 0%,
      transparent 50%
    );
    pointer-events: none;
  }
}

.element {
  background: linear-gradient(
    142deg,
    #fff4e6 0%,
    #ffffff 50%,
    #f0f7ff 100%
  ) !important;
  position: relative;

  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: radial-gradient(
      circle at 80% 20%,
      rgba(255, 153, 27, 0.05) 0%,
      transparent 50%
    );
    pointer-events: none;
  }
}
</style>
