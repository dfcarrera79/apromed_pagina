<template>
  <q-page>
    <q-page-container style="padding-top: 0px">
      <div>
        <div style="background-color: #bcbdc0">
          <div class="row justify-center q-py-md q-ma-none">
            <img src="../assets/farmacias.png" style="height: 80px" />
          </div>

          <div
            id="contacto"
            class="fit column justify-center items-center content-center q-pb-xl"
            style="background-color: #bcbdc0; height: 600px"
          >
            <div class="fit row justify-center">
              <div
                class="column justify-center items-center content-center q-pa-xl"
                style="max-width: 550px"
              >
                <div class="text-left font-bold q-pt-sm">
                  <h4 class="q-my-md">
                    <strong>Bienvenido a Farmacias Americanas</strong>
                  </h4>
                </div>
                <div class="text-subtitle1 text-left text-grey-9">
                  <p class="text-gray-7">
                    Somos una cadena de farmacias en las provincias de Loja y
                    Zamora Chinchipe, con una red de más de veinte sucursales
                    para servirle de la mejor manera.
                  </p>
                </div>
              </div>

              <q-img
                src="../assets/farma2.webp"
                class="rounded-borders"
                style="max-width: 550px; max-height: 450px"
              />
            </div>
          </div>
        </div>
      </div>

      <div id="vision" class="q-pb-md" style="background-color: #f9fafb">
        <div>
          <h3 class="text-center font-bold text-bold">Visión</h3>
        </div>

        <div class="row justify-evenly items-center content-center">
          <div class="q-pa-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 200px"
              @mouseenter="onHoverVisionClientes"
              @mouseleave="onLeaveVisionClientes"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div>
                    <div class="text-h4" style="font-family: 'Bebas Neue'">
                      A nuestros clientes
                    </div>
                  </div>
                  <div
                    :class="
                      !colorVisionClientes
                        ? 'q-pt-md text-subtitle1 text-center text-grey-9'
                        : 'q-pt-md text-subtitle1 text-center text-white'
                    "
                  >
                    <p>
                      Brindar un excelente servicio y experiencia en la compra
                      realizada de forma profesional, garantizando su bienestar
                      al dispensar productos de calidad.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>

            <q-card
              class="my-card custom-hover-background q-mt-xl"
              style="height: 340px"
              @mouseenter="onHoverVisionEquipo"
              @mouseleave="onLeaveVisionEquipo"
            >
              <q-card-section>
                <div
                  class="column justify-center items-center content-center scale-up-center fadeIn"
                >
                  <div>
                    <div class="text-h4" style="font-family: 'Bebas Neue'">
                      Sobre nuestro equipo
                    </div>
                  </div>
                  <div
                    :class="
                      !colorVisionEquipo
                        ? 'q-pt-md text-subtitle1 text-center text-grey-9'
                        : 'q-pt-md text-subtitle1 text-center text-white'
                    "
                  >
                    <p>
                      Cumplir con cada uno de los parámetros de trabajo, para
                      poder brindar a nuestros distinguidos clientes
                      satisfacción y confianza al momento de dispensar los
                      medicamentos, siendo conscientes de la importancia de la
                      salud de cada cliente, asimismo tener la certeza que el
                      trabajo de cada uno tiene una gran importancia para
                      conseguir un equipo eficaz y eficiente.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
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

        <div class="column justify-center items-center content-center">
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
                        ? 'q-pt-md text-subtitle1 text-center text-grey-9'
                        : 'q-pt-md text-subtitle1 text-center text-white'
                    "
                  >
                    <p>
                      Ofrecer medicamentos con altos estándares de calidad y
                      confiabilidad, brindando así la mejor experiencia de
                      compra, conveniencia y seguridad para nuestros clientes.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
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
                  Valores
                </div>
                <div
                  :class="
                    !colorProposito
                      ? 'text-subtitle1 text-grey-9'
                      : 'text-subtitle1 text-white'
                  "
                >
                  <ul>
                    <li>Compromiso, responsabilidad, seguridad</li>
                    <li>Humanidad, honestidad, respeto</li>
                    <li>Calidad, resolución, eficiencia</li>
                    <li>Profesionalidad</li>
                  </ul>
                </div>
              </q-card-section>

              <q-card-section class="q-pt-none"> </q-card-section>
            </q-card>
          </div>
        </div>
      </div>

      <div
        class="column justify-center q-pb-xl"
        style="background-color: #f9fafb"
      >
        <div class="fit row justify-center">
          <h3
            class="mx-auto mb-4 max-w-4xl text-center text-3xl font-bold md:text-6xl text-bold"
          >
            <span class="q-px-md"> Características destacadas </span>
          </h3>

          <div class="q-px-xl">
            <p class="text-h6 text-grey-9 text-center">
              Brindamos un excelente servicio y una experiencia de compra segura
              y sencilla. Estas son solo algunas de las características que
              hacen de Farmacias Americanas su opción número uno para todas sus
              necesidades de farmacia.
            </p>
          </div>
        </div>

        <div class="fit row wrap justify-evenly items-center content-center">
          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 450px; width: 320px"
              @mouseenter="onHoverUno"
              @mouseleave="onLeaveUno"
            >
              <q-card-section>
                <div class="column justify-center items-center content-center">
                  <div class="text-center font-bold q-pt-xl">
                    <q-btn
                      outline
                      round
                      icon="medication"
                      :color="!colorUno ? 'primary' : 'white'"
                      size="lg"
                    />
                    <h4 class="q-my-md">
                      <strong>Gran selección de productos</strong>
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
                      Ofrecemos una amplia variedad de productos en nuestras
                      tiendas que va más allá de los medicamentos, incluyendo
                      vitaminas, productos de salud y belleza, y artículos de
                      cuidado en el hogar.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 450px; width: 320px"
              @mouseenter="onHoverDos"
              @mouseleave="onLeaveDos"
            >
              <q-card-section>
                <div class="column justify-center items-center content-center">
                  <div class="text-center font-bold q-pt-xl">
                    <q-btn
                      outline
                      round
                      icon="groups_2"
                      :color="!colorDos ? 'primary' : 'white'"
                      size="lg"
                    />
                    <h4 class="q-my-md">
                      <strong>Equipo de soporte de alta calidad</strong>
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
                      Nuestro equipo de farmacéuticos y asistentes de farmacia
                      profesionales está siempre dispuesto a ayudarle con todas
                      sus necesidades. Puede contar con ellos para obtener
                      asesoramiento experto y respuesta a todas sus consultas.
                    </p>
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <div class="q-py-md">
            <q-card
              class="my-card custom-hover-background"
              style="height: 450px; width: 320px"
              @mouseenter="onHoverTres"
              @mouseleave="onLeaveTres"
            >
              <q-card-section>
                <div class="column justify-center items-center content-center">
                  <div class="text-center font-bold q-pt-xl">
                    <q-btn
                      outline
                      round
                      icon="map"
                      :color="!colorTres ? 'primary' : 'white'"
                      size="lg"
                    />
                    <h4 class="q-my-md">
                      <strong>Ubicaciones convenientes</strong>
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
                      Nuestras ubicaciones en toda la ciudad de Loja facilitan
                      la búsqueda de una farmacia cerca de usted. Cada farmacia
                      también tiene convenientes horas de atención para servirle
                      mejor.
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
        style="background-color: #bcbdc0"
      >
        <div class="fit row justify-center q-pt-xl">
          <q-carousel
            animated
            v-model="slide"
            swipeable
            infinite
            :autoplay="autoplay"
            arrows
            transition-prev="slide-right"
            transition-next="slide-left"
            @mouseenter="autoplay = false"
            @mouseleave="autoplay = true"
            style="width: 460px"
          >
            <q-carousel-slide :name="1" img-src="..//assets/farma1.webp" />
            <q-carousel-slide :name="2" img-src="..//assets/farma3.webp" />
            <q-carousel-slide :name="3" img-src="..//assets/farma4.webp" />
          </q-carousel>

          <div class="column q-pa-xl" style="max-width: 550px">
            <div class="text-left font-bold q-pt-sm">
              <h4 class="q-my-md">
                <strong>¿Listo para empezar?</strong>
              </h4>
            </div>
            <div class="text-subtitle1 text-left text-grey-9">
              <p class="text-gray-7">
                Encuentra la farmacia americana más cercana a ti y experimenta
                la calidad de nuestro servicio.
              </p>
            </div>
            <q-scroll-area
              :thumb-style="thumbStyle"
              :bar-style="barStyle"
              style="height: 400px; max-width: 320px"
            >
              <div
                class="q-pa-sm"
                v-for="index in direcciones.length"
                :key="index"
              >
                <q-btn outline color="orange" no-caps style="width: 290px">
                  <div
                    class="text-grey-9"
                    @click="openGoogleMaps(direcciones[index - 1])"
                  >
                    {{ direcciones[index - 1] }}<br />{{ telefonos[index - 1] }}
                  </div>
                  <q-tooltip class="bg-grey-8 text-body2" :offset="[10, 10]">
                    Ubicanos en Google Maps
                  </q-tooltip>
                </q-btn>
              </div>
            </q-scroll-area>
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
      />

      <div class="row justify-center bg-grey-9">
        <div class="q-pa-md">
          <a href="https://www.facebook.com/farmaciasamericana" target="_blank">
            <q-avatar>
              <img src="../assets/facebook_logo.svg" />
            </q-avatar>
            <q-tooltip class="bg-grey-8 text-body2" :offset="[10, 10]">
              Nuestro Facebook
            </q-tooltip>
          </a>
        </div>

        <div class="q-pa-md">
          <a href="https://wa.me/593968822033" target="_blank">
            <q-avatar>
              <img src="../assets/whatsapp.svg" />
            </q-avatar>
            <q-tooltip class="bg-grey-8 text-body2" :offset="[10, 10]">
              Escríbenos por WhatsApp
            </q-tooltip>
          </a>
        </div>

        <div class="q-py-md q-ml-md q-mt-xs">
          <q-btn
            outline
            round
            color="primary"
            icon="email"
            size="md"
            href="mailto:farmaciasamericanas@apromedloja.com"
            target="_blank"
          >
            <q-tooltip class="bg-grey-8 text-body2" :offset="[10, 10]">
              Envíanos un correo electrónico
            </q-tooltip>
          </q-btn>
        </div>
      </div>

      <q-separator />
      <div>
        <div class="row justify-evenly bg-grey">
          <p class="text-caption text-white">
            Copyright &copy; 2023 Apromed S.A.S.
          </p>
        </div>
      </div>
      <!-- Footer End -->
    </q-page-container>
  </q-page>
</template>

<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue';

// Data
const showScrollToTopButton = ref(false);
const slide = ref(1);
const autoplay = ref(true);
const colorMision = ref(false);
const colorVisionClientes = ref(false);
const colorVisionEquipo = ref(false);
const colorProposito = ref(false);
const colorUno = ref(false);
const colorDos = ref(false);
const colorTres = ref(false);
const direcciones = [
  'Lauro Guerrero y Rocafuerte',
  'Bolívar y Rocafuerte',
  'Ramón Pinto entre Miguel Riofrío y Azuay',
  '10 de Agosto y Bernardo Valdiviezo',
  '18 de Noviembre y Miguel Riofrío',
  'Bolívar y Azuay',
  'Av. Universitaria y Rocafuerte',
  'Lauro Guerreo y 10 de Agosto',
  'Av. Universitaria y 10 de Agosto',
  '10 de Agosto y Carlos Ojeda (Gonzanamá)',
  'Velazco Ibarra (Cariamanga)',
  'Jorge Mosquera (El Pangui)',
  '18 de Noviembre y Gonzanamá',
  'Luís Fernando de la Vega y Diego Vaca',
  'Eugenio Espejo y 24 de Mayo (Catamayo)',
  '10 de Agosto y Juan Vela (Macará)',
  'Vela Dávila y Cuenca (Catamayo)',
  'Calle Guayaquil y Machala',
  '12 de Diciembre y Sebastián de Benalcázar (Celica)',
  'Av. Ivan Riofrío y Orquídeas (Yantzaza)',
  'Lazaro Vaca (Macará)',
];
const telefonos = [
  '2572798',
  '2570266',
  '2565611',
  '2724919',
  '2581216',
  '2732253',
  '2730148',
  '2726764',
  '2726039',
  '2664687',
  '2688801',
  '2416497',
  '2724833',
  '2640171',
  '2678643',
  '3141011',
  '0968070135',
  '0968822033',
  '0985890638',
  '0985890036',
  '',
];
const thumbStyle = {
  right: '4px',
  borderRadius: '5px',
  backgroundColor: '#ee7600',
  width: '5px',
  opacity: 0.75,
};
const barStyle = {
  right: '2px',
  borderRadius: '9px',
  backgroundColor: '#ee7600',
  width: '9px',
  opacity: 0.2,
};

// Methods
const openGoogleMaps = (address: string) => {
  // Extraer el contenido entre paréntesis
  const matches = address.match(/\(([^)]*)\)/);
  let locality = '';

  if (matches && matches.length > 1) {
    locality = matches[1]; // Obtener el contenido entre paréntesis
  }

  // Remover el contenido entre paréntesis
  const modifiedAddress = address.replace(/\([^)]*\)/g, '');

  // Agregar ", Loja, Ecuador" al final
  const finalAddress = `${modifiedAddress}, ${locality}, Loja, Ecuador`;

  const encodedAddress = encodeURIComponent(finalAddress);

  const url = `https://www.google.com/maps?q=${encodedAddress}`;
  window.open(url, '_blank'); // Abre en una nueva pestaña o ventana
};

// Mostrar el botón de regreso cuando se hace scroll
const handleScroll = () => {
  const scrollY = window.scrollY;
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

function onHoverMision() {
  colorMision.value = true;
}

function onLeaveMision() {
  colorMision.value = false;
}

function onHoverVisionClientes() {
  colorVisionClientes.value = true;
}

function onLeaveVisionClientes() {
  colorVisionClientes.value = false;
}

function onHoverVisionEquipo() {
  colorVisionEquipo.value = true;
}

function onLeaveVisionEquipo() {
  colorVisionEquipo.value = false;
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
</script>

<style lang="scss" scoped>
.hover-color {
  color: white;
  transition: color 0.3s;

  &:hover {
    color: #ee7600;
  }
}

.custom-hover-background {
  &:hover {
    background-color: #ff991b;
    transition: background-color 0.3s; // Opcional: agrega una transición suave
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

.scroll-to-top-button {
  position: fixed;
  bottom: 20px; // Ajusta la distancia desde la parte inferior de la página
  right: 20px; // Ajusta la distancia desde la derecha de la página
  z-index: 1000; // Asegura que esté por encima de otros elementos
  // Puedes agregar otros estilos de diseño según tus preferencias
}
</style>
