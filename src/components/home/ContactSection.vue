<template>
  <div
    id="contacto"
    class="fit column justify-center items-center content-center q-pb-xl"
    :class="
      appStore.darkMode
        ? 'fit column justify-center items-center content-center q-pb-xl element-dark'
        : 'fit column justify-center items-center content-center q-pb-xl element'
    "
    style="background-color: #f9fafb; height: 600px"
  >
    <div>
      <h3
        class="mx-auto mb-4 max-w-4xl text-center text-3xl font-bold md:text-6xl text-bold"
      >
        Contáctanos
      </h3>
    </div>

    <div class="fit row justify-center">
      <q-img
        src="https://res.cloudinary.com/dvy167slj/image/upload/f_auto,q_auto/v1/apromed/medicamentos"
        class="rounded-borders"
        style="max-width: 450px; max-height: 450px"
      />

      <div
        class="column justify-center items-center content-center q-pa-xl"
        style="max-width: 350px"
      >
        <div class="text-left font-bold q-pt-sm">
          <h4 class="q-my-md">
            <strong>Queremos Ser Parte de su Equipo de Salud</strong>
          </h4>
        </div>
        <div class="text-subtitle1 text-left">
          <p class="text-gray-7">
            En Apromed, deseamos formar parte de su equipo de salud. Ponte en
            contacto con nosotros para empezar a disfrutar de nuestros productos
            y servicios de alta calidad. Juntos, podemos hacer una diferencia en
            la salud y el bienestar de su comunidad.
          </p>
        </div>
      </div>
    </div>

    <div
      class="fit row wrap justify-evenly items-center content-center"
      style="transform: translateY(-10px)"
    >
      <div class="q-py-md">
        <ContactCard
          title="Nuestras Oficinas"
          icon="location_on"
          info="Av. Eugenio Espejo 200-31 Y Adolfo Valarezo, Loja, Ecuador"
          tooltip-text="Ubicanos en Google Maps"
          :on-click="openGoogleMaps"
        />
      </div>

      <div class="q-py-md">
        <ContactCard
          title="Email"
          icon="email"
          info="info@apromedloja.com"
          href="mailto:info@apromedloja.com"
          tooltip-text="Envíanos un correo electrónico"
        />
      </div>

      <div class="q-py-md">
        <ContactCard
          title="Teléfonos"
          icon="phone"
          info="072713525 - 072713443"
        />
      </div>

      <div class="q-py-md">
        <ContactCard
          title="TeleVentas"
          info="0988130131"
          href="https://wa.me/593988130131"
          custom-icon="src/assets/whatsapp.svg"
          tooltip-text="Escríbenos por WhatsApp"
        />
      </div>

      <div class="q-py-md">
        <ContactCard
          title="Bodega"
          info="0969884332"
          href="https://wa.me/593969884332"
          custom-icon="src/assets/whatsapp.svg"
          tooltip-text="Escríbenos por WhatsApp"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useAuthStore } from '../../stores/auth';
import ContactCard from '../shared/ContactCard.vue';

const appStore = useAuthStore();

const openGoogleMaps = () => {
  const latitude = -3.9925115144793994;
  const longitude = -79.21108921570423;
  const url = `https://www.google.com/maps?q=${latitude},${longitude}`;
  window.open(url, '_blank');
};
</script>

<style lang="scss" scoped>
.element-dark {
  background: linear-gradient(
    142deg,
    #1a1a2e 0%,
    #003d7a 50%,
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
      circle at 70% 30%,
      rgba(255, 153, 27, 0.08) 0%,
      transparent 60%
    );
    pointer-events: none;
  }
}

.element {
  background: linear-gradient(
    142deg,
    #f0f7ff 0%,
    #ffffff 50%,
    #fff4e6 100%
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
      circle at 30% 70%,
      rgba(0, 61, 122, 0.03) 0%,
      transparent 60%
    );
    pointer-events: none;
  }
}
</style>
