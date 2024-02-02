<template>
  <q-page>
    <q-page-container style="padding-top: 20px">
      <div class="q-pa-none">
        <div>
          <div class="row justify-center">
            <img src="../assets/logo_apromed.png" style="height: 150px" />
          </div>

          <div class="q-pb-xl q-px-sm fadeIn">
            <q-carousel
              swipeable
              animated
              arrows
              :autoplay="autoplay"
              v-model="slide"
              v-model:fullscreen="fullscreen"
              infinite
              style="height: 480px; max-width: 920px; margin: 0 auto"
            >
              <q-carousel-slide :name="1">
                <q-img
                  src="../assets/img1.webp"
                  height="400px"
                  class="rounded-borders"
                />
                <div class="q-mt-md text-center">
                  <p class="text-body1 text-grey-9">
                    <strong> Tu salud, nuestra prioridad. </strong>
                  </p>
                </div>
              </q-carousel-slide>
              <q-carousel-slide :name="2">
                <q-img
                  src="../assets/img2.webp"
                  height="400px"
                  class="rounded-borders"
                />
                <div class="q-mt-md text-center">
                  <p class="text-body1 text-grey-9">
                    <strong> Cuidando vidas, distribuyendo esperanza </strong>
                  </p>
                </div>
              </q-carousel-slide>
              <q-carousel-slide :name="3">
                <q-img
                  src="../assets/img3.webp"
                  height="400px"
                  class="rounded-borders"
                />
                <div class="q-mt-md text-center">
                  <p class="text-body1 text-grey-9">
                    <strong> Juntos hacia un futuro más saludable </strong>
                  </p>
                </div>
              </q-carousel-slide>
            </q-carousel>
          </div>
        </div>
      </div>

      <div
        id="quienesSomos"
        class="column justify-center q-pb-md"
        style="background-color: #bcbdc0"
      >
        <div>
          <h3 class="text-center font-bold text-bold">Quiénes Somos</h3>
        </div>

        <div class="row justify-center items-center content-center">
          <div class="q-pa-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 240px"
              @mouseenter="onHoverMision"
              @mouseleave="onLeaveMision"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div>
                    <div class="text-h4" style="font-family: 'Bebas Neue'">
                      Nuestra Misión
                    </div>
                  </div>
                  <div
                    :class="
                      !colorMision
                        ? 'q-pt-md text-subtitle2 text-justify text-grey-9'
                        : 'q-pt-md text-subtitle2 text-justify text-white'
                    "
                  >
                    <p>
                      Distribuir productos farmacéuticos con un compromiso
                      inquebrantable hacia la calidad, la seguridad laboral y la
                      eficiencia. Nos esforzamos por mantener las condiciones
                      óptimas de nuestros productos en beneficio de la salud y
                      el bienestar de nuestros clientes.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-pa-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 240px"
              @mouseenter="onHoverVision"
              @mouseleave="onLeaveVision"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div>
                    <div class="text-h4" style="font-family: 'Bebas Neue'">
                      Nuestra Visión
                    </div>
                  </div>
                  <div
                    :class="
                      !colorVision
                        ? 'q-pt-md text-subtitle2 text-justify text-grey-9'
                        : 'q-pt-md text-subtitle2 text-justify text-white'
                    "
                  >
                    <p>
                      Ser un referente en la distribución de productos
                      farmacéuticos a nivel del austro y ampliar nuestro mercado
                      a nivel nacional, siendo reconocida como una empresa
                      comprometida con el fortalecimiento de sus procesos
                      internos de control, cumplimiento legal y responsabilidad
                      social.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>
        </div>

        <div class="row justify-center q-py-xl">
          <q-card
            class="my-card custom-hover-background"
            style="max-width: 740px"
            @mouseenter="onHoverProposito"
            @mouseleave="onLeaveProposito"
          >
            <q-card-section>
              <div
                class="text-h4 text-center scale-up-center fadeIn"
                style="font-family: 'Bebas Neue'"
              >
                Nuestro propósito
              </div>
              <div
                :class="
                  !colorProposito
                    ? 'q-pt-md text-subtitle2 text-justify text-grey-9'
                    : 'q-pt-md text-subtitle2 text-justify text-white'
                "
              >
                <p>
                  Mejorar la salud y el bienestar de las comunidades que
                  servimos a través de una distribución farmacéutica de calidad
                  y una dedicación apasionada hacia la salud y el bienestar de
                  nuestros clientes.
                </p>
              </div>
            </q-card-section>

            <q-card-section class="q-pt-none"> </q-card-section>
          </q-card>
        </div>
      </div>

      <div
        class="fit column wrap justify-center items-center content-center q-pb-xl"
        style="background-color: #f9fafb"
      >
        <div class="fit row justify-center">
          <h3
            class="mx-auto mb-4 max-w-4xl text-center text-3xl font-bold md:text-6xl text-bold"
          >
            Cómo Trabajamos
          </h3>
          <div class="q-px-xl">
            <p class="text-h6 text-grey-9 text-center">
              En Apromed seguimos un riguroso proceso para asegurar la calidad y
              seguridad de los productos que entregamos. Aquí le mostramos un
              vistazo a nuestro método de trabajo:
            </p>
          </div>
        </div>

        <div class="fit row wrap justify-evenly items-center content-center">
          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background bg-color"
              style="height: 450px; width: 270px"
              @mouseenter="onHoverUno"
              @mouseleave="onLeaveUno"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div class="text-center font-bold q-pt-xl">
                    <q-btn
                      outline
                      round
                      :color="!colorUno ? 'primary' : 'white'"
                      size="lg"
                    >
                      <strong>1</strong>
                    </q-btn>
                    <h4 class="q-my-md">
                      <strong>Selección de Productos</strong>
                    </h4>
                  </div>
                  <div
                    :class="
                      !colorUno
                        ? 'text-subtitle1 text-center text-grey-9'
                        : 'text-subtitle1 text-center text-white'
                    "
                  >
                    <p>
                      Seleccionamos los productos más adecuados de acuerdo a la
                      demanda del mercado y los análisis clínicos, asegurando
                      siempre la máxima calidad y efectividad.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 450px; width: 270px"
              @mouseenter="onHoverDos"
              @mouseleave="onLeaveDos"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div class="text-center font-bold q-pt-xl">
                    <q-btn
                      outline
                      round
                      :color="!colorDos ? 'primary' : 'white'"
                      size="lg"
                    >
                      <strong>2</strong>
                    </q-btn>
                    <h4 class="q-my-md">
                      <strong>Control Riguroso</strong>
                    </h4>
                  </div>
                  <div
                    :class="
                      !colorDos
                        ? 'text-subtitle1 text-center text-grey-9'
                        : 'text-subtitle1 text-center text-white'
                    "
                  >
                    <p>
                      Cada producto que llega a nuestras manos pasa por un
                      estricto proceso de control de calidad y seguridad,
                      garantizado por nuestras certificaciones de alto nivel.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 450px; width: 270px"
              @mouseenter="onHoverTres"
              @mouseleave="onLeaveTres"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div class="text-center font-bold q-pt-xl">
                    <q-btn
                      outline
                      round
                      :color="!colorTres ? 'primary' : 'white'"
                      size="lg"
                    >
                      <strong>3</strong>
                    </q-btn>
                    <h4 class="q-my-md">
                      <strong>Distribución</strong>
                    </h4>
                  </div>
                  <div
                    :class="
                      !colorTres
                        ? 'text-subtitle1 text-center text-grey-9'
                        : 'text-subtitle1 text-center text-white'
                    "
                  >
                    <p>
                      Operamos una red de distribución eficiente que garantiza
                      que nuestros productos lleguen óptimamente a cada uno de
                      nuestros clientes.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 450px; width: 270px"
              @mouseenter="onHoverCuatro"
              @mouseleave="onLeaveCuatro"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div class="text-center font-bold q-pt-xl">
                    <q-btn
                      outline
                      round
                      :color="!colorCuatro ? 'primary' : 'white'"
                      size="lg"
                    >
                      <strong>4</strong>
                    </q-btn>
                    <h4 class="q-my-md">
                      <strong>Soporte Constante</strong>
                    </h4>
                  </div>
                  <div
                    :class="
                      !colorCuatro
                        ? 'text-subtitle1 text-center text-grey-9'
                        : 'text-subtitle1 text-center text-white'
                    "
                  >
                    <p>
                      Ofrecemos soporte constante a nuestros clientes durante
                      todo el proceso, desde la selección del producto hasta su
                      entrega. Su satisfacción es nuestra prioridad.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>
        </div>
      </div>

      <div
        class="fit column wrap justify-center items-center content-center q-pb-xl"
        style="background-color: #bcbdc0; height: 600px"
      >
        <div class="fit column justify-center">
          <h3
            class="mx-auto mb-4 max-w-4xl text-center text-3xl font-bold md:text-6xl text-bold"
          >
            Nos Destacamos
          </h3>
          <div class="q-px-xl">
            <p class="text-h6 text-center text-grey-9">
              En Apromed, nos enorgullece ofrecer productos y servicios que
              destacan en la industria farmacéutica. Aquí algunos de ellos:
            </p>
          </div>
        </div>

        <div class="fit row wrap justify-evenly items-center content-center">
          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 588px; width: 270px"
              @mouseenter="onHoverSeguridad"
              @mouseleave="onLeaveSeguridad"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div class="text-center font-bold q-pt-xl">
                    <q-btn
                      outline
                      round
                      :color="!colorSeguridad ? 'primary' : 'white'"
                      icon="security"
                      size="lg"
                    />
                    <h4 class="q-my-md">
                      <strong>Seguridad Garantizada</strong>
                    </h4>
                  </div>
                  <div
                    :class="
                      !colorSeguridad
                        ? 'text-subtitle1 text-center text-grey-9'
                        : 'text-subtitle1 text-center text-white'
                    "
                  >
                    <p>
                      Con Apromed, puede estar seguro de que todos nuestros
                      productos cumplen con los más altos estándares de
                      seguridad. Nuestro control de calidad estricto y riguroso
                      asegura que cada producto que ofrecemos es seguro y
                      efectivo para su uso.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 588px; width: 270px"
              @mouseenter="onHoverEntrega"
              @mouseleave="onLeaveEntrega"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div class="text-center font-bold q-pt-xl">
                    <q-btn
                      outline
                      round
                      :color="!colorEntrega ? 'primary' : 'white'"
                      icon="rocket_launch"
                      size="lg"
                    />
                    <h4 class="q-my-md">
                      <strong>Entrega Rápida y Eficiente</strong>
                    </h4>
                  </div>
                  <div
                    :class="
                      !colorEntrega
                        ? 'text-subtitle1 text-center text-grey-9'
                        : 'text-subtitle1 text-center text-white'
                    "
                  >
                    <p>
                      Operamos una red de distribución rápida y eficiente para
                      asegurar que los productos farmacéuticos que necesita
                      lleguen a tiempo y en la mejor condición posible. Este
                      nivel de eficiencia nos permite satisfacer las necesidades
                      de nuestros clientes.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 588px; width: 270px"
              @mouseenter="onHoverSoporte"
              @mouseleave="onLeaveSoporte"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div class="text-center font-bold q-pt-xl">
                    <q-btn
                      outline
                      round
                      :color="!colorSoporte ? 'primary' : 'white'"
                      icon="support_agent"
                      size="lg"
                    />
                    <h4 class="q-my-md">
                      <strong>Soporte al Cliente</strong>
                    </h4>
                  </div>
                  <div
                    :class="
                      !colorSoporte
                        ? 'text-subtitle1 text-center text-grey-9'
                        : 'text-subtitle1 text-center text-white'
                    "
                  >
                    <p>
                      Nuestro equipo de servicio al cliente está disponible para
                      ayudarlo en cada etapa del proceso. Ya sea que tenga
                      preguntas sobre nuestros productos, necesite ayuda con su
                      pedido o tenga cualquier otra consulta, nuestro equipo
                      dedicado está listo para ayudarlo.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>
        </div>
      </div>

      <div
        id="contacto"
        class="fit column justify-center items-center content-center q-pb-xl"
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
            src="../assets/medicamentos.webp"
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
            <div class="text-subtitle1 text-left text-grey-9">
              <p class="text-gray-7">
                En Apromed, deseamos formar parte de su equipo de salud. Ponte
                en contacto con nosotros para empezar a disfrutar de nuestros
                productos y servicios de alta calidad. Juntos, podemos hacer una
                diferencia en la salud y el bienestar de su comunidad.
              </p>
            </div>
          </div>
        </div>

        <div
          class="fit row wrap justify-evenly items-center content-center"
          style="transform: translateY(-10px)"
        >
          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 220px; width: 250px"
              @mouseenter="onHoverOficinas"
              @mouseleave="onLeaveOficinas"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div>
                    <div class="text-h4" style="font-family: 'Bebas Neue'">
                      Nuestras Oficinas
                    </div>
                  </div>
                  <div class="q-py-md">
                    <q-btn
                      outline
                      round
                      :color="!colorOficinas ? 'primary' : 'white'"
                      icon="location_on"
                      size="lg"
                      @click="openGoogleMaps"
                    >
                      <q-tooltip
                        class="bg-grey-8 text-body2"
                        :offset="[10, 10]"
                      >
                        Ubicanos en Google Maps
                      </q-tooltip>
                    </q-btn>
                  </div>
                  <div class="text-subtitle2 text-center text-grey-9">
                    Av. Eugenio Espejo 200-31 Y Adolfo Valarezo, Loja, Ecuador
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 220px; width: 250px"
              @mouseenter="onHoverEmail"
              @mouseleave="onLeaveEmail"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div>
                    <div class="text-h4" style="font-family: 'Bebas Neue'">
                      Email
                    </div>
                  </div>
                  <div class="q-py-md">
                    <q-btn
                      outline
                      round
                      :color="!colorEmail ? 'primary' : 'white'"
                      icon="email"
                      size="lg"
                      href="mailto:info@apromedloja.com"
                      target="_blank"
                    >
                      <q-tooltip
                        class="bg-grey-8 text-body2"
                        :offset="[10, 10]"
                      >
                        Envíanos un correo electrónico
                      </q-tooltip>
                    </q-btn>
                  </div>
                  <div class="text-subtitle2 text-center text-grey-9">
                    info@apromedloja.com
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 220px; width: 250px"
              @mouseenter="onHoverTelefonos"
              @mouseleave="onLeaveTelefonos"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div>
                    <div class="text-h4" style="font-family: 'Bebas Neue'">
                      Teléfonos
                    </div>
                  </div>
                  <div class="q-py-md">
                    <q-btn
                      outline
                      icon="phone"
                      round
                      :color="!colorTelefonos ? 'primary' : 'white'"
                      size="lg"
                    />
                  </div>
                  <div class="text-subtitle2 text-center text-grey-9">
                    072713525 - 072713443
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 220px; width: 250px"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div>
                    <div class="text-h4" style="font-family: 'Bebas Neue'">
                      TeleVentas
                    </div>
                  </div>
                  <div class="q-py-md">
                    <q-btn
                      round
                      style="background: #ffffff; color: white"
                      size="lg"
                      href="https://wa.me/593988130131"
                      target="_blank"
                    >
                      <q-avatar>
                        <img src="../assets/whatsapp.svg" />
                      </q-avatar>
                      <q-tooltip
                        class="bg-grey-8 text-body2"
                        :offset="[10, 10]"
                      >
                        Escríbenos por WhatsApp
                      </q-tooltip>
                    </q-btn>
                  </div>
                  <div class="text-subtitle2 text-center text-grey-9">
                    0988130131
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 220px; width: 250px"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div>
                    <div class="text-h4" style="font-family: 'Bebas Neue'">
                      Bodega
                    </div>
                  </div>
                  <div class="q-py-md">
                    <q-btn
                      round
                      style="background: #ffffff; color: white"
                      size="lg"
                      href="https://wa.me/593969884332"
                      target="_blank"
                    >
                      <q-avatar>
                        <img src="../assets/whatsapp.svg" />
                      </q-avatar>
                      <q-tooltip
                        class="bg-grey-8 text-body2"
                        :offset="[10, 10]"
                      >
                        Escríbenos por WhatsApp
                      </q-tooltip>
                    </q-btn>
                  </div>
                  <div class="text-subtitle2 text-center text-grey-9">
                    0969884332
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>
        </div>
      </div>

      <!-- Footer Start -->

      <!-- Botón de regresar al inicio -->
      <q-btn
        v-if="showScrollToTopButton"
        dense
        round
        color="primary"
        icon="keyboard_arrow_up"
        class="q-px-sm scroll-to-top-button"
        @click="scrollToTop"
      >
        <q-tooltip
          class="bg-grey-8 text-body2"
          transition-show="scale"
          transition-hide="scale"
          anchor="center right"
          self="center left"
        >
          <span style="white-space: nowrap">Ir al inicio</span>
        </q-tooltip>
      </q-btn>

      <div
        :class="
          !scrolled
            ? 'fixed-bottom-right fixed-whatsapp-btn'
            : 'fixed-bottom-right whatsapp-btn'
        "
      >
        <q-btn
          flat
          round
          size="sm"
          target="_blank"
          href="https://wa.me/593988130131"
        >
          <q-avatar>
            <img src="../assets/whatsapp.svg" />
          </q-avatar>
          <q-tooltip
            class="bg-grey-8 text-body2"
            transition-show="scale"
            transition-hide="scale"
            anchor="center right"
            self="center left"
          >
            <span style="white-space: nowrap">Escríbenos por WhatsApp</span>
          </q-tooltip>
        </q-btn>
      </div>

      <q-separator />

      <FootApromed />
    </q-page-container>
  </q-page>
</template>

<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue';
import FootApromed from '../components/FootApromed.vue';

// Data
const slide = ref(1);
const autoplay = ref(true);
const fullscreen = ref(false);
const showScrollToTopButton = ref(false);
const colorMision = ref(false);
const colorVision = ref(false);
const colorProposito = ref(false);
const colorUno = ref(false);
const colorDos = ref(false);
const colorTres = ref(false);
const colorCuatro = ref(false);
const colorSeguridad = ref(false);
const colorEntrega = ref(false);
const colorSoporte = ref(false);
const colorOficinas = ref(false);
const colorEmail = ref(false);
const colorTelefonos = ref(false);
const scrolled = ref(false);

// Methods
const openGoogleMaps = () => {
  const latitude = -3.9925115144793994;
  const longitude = -79.21108921570423;
  const url = `https://www.google.com/maps?q=${latitude},${longitude}`;
  window.open(url, '_blank'); // Abre en una nueva pestaña o ventana
};

// Mostrar el botón de regreso cuando se hace scroll
const handleScroll = () => {
  const scrollY = window.scrollY;
  scrolled.value = window.scrollY > 0;
  showScrollToTopButton.value = scrollY > 200; // Cambia 200 por la posición a partir de la cual quieres mostrar el botón
};

// Desplazarse al inicio de la página
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
};

// Agregar el manejador de eventos al hacer scroll
onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

// Quitar el manejador de eventos al desmontar el componente
onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});

const elements = document.querySelectorAll('.fadeIn');

const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      entry.target.classList.add('animated');
    }
  });
});

elements.forEach((element) => {
  observer.observe(element);
});

function onHoverMision() {
  colorMision.value = true;
}

function onLeaveMision() {
  colorMision.value = false;
}

function onHoverVision() {
  colorVision.value = true;
}

function onLeaveVision() {
  colorVision.value = false;
}

function onHoverProposito() {
  colorProposito.value = true;
}

function onLeaveProposito() {
  colorProposito.value = false;
}

function onHoverUno() {
  colorUno.value = true;
}

function onLeaveUno() {
  colorUno.value = false;
}

function onHoverDos() {
  colorDos.value = true;
}

function onLeaveDos() {
  colorDos.value = false;
}

function onHoverTres() {
  colorTres.value = true;
}

function onLeaveTres() {
  colorTres.value = false;
}

function onHoverCuatro() {
  colorCuatro.value = true;
}

function onLeaveCuatro() {
  colorCuatro.value = false;
}

function onHoverSeguridad() {
  colorSeguridad.value = true;
}

function onLeaveSeguridad() {
  colorSeguridad.value = false;
}

function onHoverEntrega() {
  colorEntrega.value = true;
}

function onLeaveEntrega() {
  colorEntrega.value = false;
}

function onHoverSoporte() {
  colorSoporte.value = true;
}

function onLeaveSoporte() {
  colorSoporte.value = false;
}

function onHoverOficinas() {
  colorOficinas.value = true;
}

function onLeaveOficinas() {
  colorOficinas.value = false;
}

function onHoverEmail() {
  colorEmail.value = true;
}

function onLeaveEmail() {
  colorEmail.value = false;
}

function onHoverTelefonos() {
  colorTelefonos.value = true;
}

function onLeaveTelefonos() {
  colorTelefonos.value = false;
}

// Agregar y quitar el listener del evento de desplazamiento
onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style lang="scss" scoped>
.hover-color {
  color: white;
  transition: color 0.3s;

  &:hover {
    color: #ee7600;
  }
}

.text-white a {
  color: inherit; // Utiliza el color heredado del texto circundante
  text-decoration: none; // Elimina el subrayado del enlace si lo hay
}

.my-card {
  width: 100%;
  max-width: 350px;
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out,
    opacity 0.3s ease-in-out;
  border-radius: 10px;

  &:hover {
    transform: translateY(-10px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2); // Agrega una sombra al hacer hover
    opacity: 0.9; // Reduce ligeramente la opacidad al hacer hover
  }

  &.animate-on-scroll {
    opacity: 1;
    transform: translateY(0);
    transition: transform 0.5s ease-in-out, box-shadow 0.5s ease-in-out,
      opacity 0.5s ease-in-out;
  }
}

.custom-hover-background {
  &:hover {
    background-color: #ff991b;
    transition: background-color 0.3s; // Opcional: agrega una transición suave
  }
}

.scroll-to-top-button {
  position: fixed;
  bottom: 20px; // Ajusta la distancia desde la parte inferior de la página
  right: 20px; // Ajusta la distancia desde la derecha de la página
  z-index: 1000; // Asegura que esté por encima de otros elementos
  // Puedes agregar otros estilos de diseño según tus preferencias
}

.fadeIn {
  animation: fadeIn 1s ease-in-out;
  animation-fill-mode: forwards;
}

@keyframes fade-in {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

@keyframes scale-up-center {
  0% {
    transform: scale(0);
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

.scale-up-center {
  animation: scale-up-center 0.4s cubic-bezier(0, 0.5, 0, 1) both;
  animation-delay: 0.5s;
  animation-fill-mode: forwards;
}

.whatsapp-btn {
  margin-right: 15px;
  margin-bottom: 70px;
  transition: transform 0.5s ease;
}

.fixed-whatsapp-btn {
  margin-right: 15px;
  margin-bottom: 70px;
  transform: translateY(40px); /* Adjust the initial position */
}
</style>
