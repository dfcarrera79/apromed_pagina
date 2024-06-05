<template>
  <q-layout view="lHh Lpr lFf">
    <q-header
      elevated
      style="background-color: rgba(222, 218, 218, 0.7)"
      height-hint="98"
    >
      <q-toolbar>
        <q-toolbar-title>
          <a href="/">
            <img
              src="https://res.cloudinary.com/dvy167slj/image/upload/f_auto,q_auto/v1/apromed/logo_apromed"
              style="height: 70px"
            />
          </a>
        </q-toolbar-title>

        <div
          class="row justify-evenly"
          v-if="!($q.screen.lt.md || $q.screen.lt.sm)"
        >
          <div class="q-px-sm hover-color text-grey-9">
            <q-btn dense flat no-caps to="/">
              <q-icon left name="home" size="xs" />
              <div class="hover-color text-grey-9">Inicio</div>
            </q-btn>
          </div>
          <div class="q-px-sm hover-color text-grey-9">
            <q-btn
              dense
              flat
              label="Quiénes Somos"
              no-caps
              class="q-px-sm"
              to="/"
              @click="redirectTo(scrollToQuienesSomos)"
            />
          </div>
          <div class="q-px-sm hover-color text-grey-9">
            <q-btn
              dense
              flat
              label="Contáctanos"
              no-caps
              class="q-px-sm"
              @click="redirectTo(scrollToContacto)"
            />
          </div>
          <div class="q-px-sm hover-color text-grey-9">
            <q-btn
              dense
              flat
              label="Farmacias Americanas"
              no-caps
              class="q-px-sm"
              to="/farmacias"
            />
          </div>

          <div class="q-px-sm hover-color text-grey-9">
            <q-btn
              dense
              flat
              label="Descargar Factura"
              no-caps
              class="q-px-sm"
              href="https://www.loxasoluciones-cloud.com:8081/#/login?redirect=/"
              target="_blank"
            />
          </div>

          <div class="q-px-sm hover-color text-grey-9">
            <q-btn
              dense
              flat
              label="Correo Institucional"
              no-caps
              class="q-px-sm"
              href="https://www.apromedloja.com/webmail/"
              target="_blank"
            />
          </div>

          <div class="q-px-sm hover-color text-grey-9">
            <q-btn
              dense
              flat
              label="Gestión Nómina"
              no-caps
              class="q-px-sm"
              href="https://apromedfarmaloja-cloud.com:3020/#/login"
              target="_blank"
            />
          </div>

          <div class="q-px-sm hover-color text-grey-9">
            <q-btn-dropdown
              dense
              flat
              label="Documentos"
              no-caps
              class="q-px-sm"
            >
              <q-list>
                <q-item clickable v-close-popup>
                  <q-item-section>
                    <q-item-label clickable @click="onButtonClick(1)">
                      Clientes de Apromed</q-item-label
                    >
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup>
                  <q-item-section>
                    <q-item-label clickable @click="onButtonClick(2)"
                      >Usuarios de Apromed</q-item-label
                    >
                  </q-item-section>
                </q-item>
              </q-list>
            </q-btn-dropdown>
          </div>
          <div class="q-px-sm hover-color text-grey-9">
            <q-btn-dropdown dense flat label="Reclamos" no-caps class="q-px-sm">
              <q-list>
                <q-item clickable v-close-popup>
                  <q-item-section>
                    <q-item-label clickable @click="onItemClick(1)">
                      Clientes de Apromed</q-item-label
                    >
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup>
                  <q-item-section>
                    <q-item-label clickable @click="onItemClick(2)"
                      >Usuarios de Apromed</q-item-label
                    >
                  </q-item-section>
                </q-item>
              </q-list>
            </q-btn-dropdown>
          </div>
        </div>

        <q-toggle
          :model-value="dark.isActive"
          checked-icon="dark_mode"
          unchecked-icon="light_mode"
          size="3rem"
          @update:model-value="(val) => dark.set(val)"
        />

        <q-btn
          dense
          flat
          round
          icon="menu"
          @click="toggleRightDrawer"
          v-if="$q.screen.lt.md"
        />
      </q-toolbar>
    </q-header>

    <q-drawer
      show-if-above
      v-model="rightDrawerOpen"
      side="right"
      bordered
      v-if="$q.screen.lt.md"
    >
      <div class="q-pa-sm">
        <q-img
          fit="fill"
          class="absolute-top"
          src="../assets/logo_apromed.png"
          style="height: 150px; weight: 250px"
        />
      </div>
      <q-scroll-area
        style="
          height: calc(100% - 150px);
          margin-top: 150px;
          border-right: 1px solid #ddd;
        "
      >
        <q-list padding>
          <q-item clickable v-ripple active-class="my-menu-link" to="/">
            <q-item-section avatar>
              <q-icon name="home" />
            </q-item-section>
            <q-item-section>
              <q-item-label class="text-h6">Inicio</q-item-label>
            </q-item-section>
          </q-item>

          <q-item
            clickable
            v-ripple
            active-class="my-menu-link"
            to="/farmacias"
          >
            <q-item-section avatar>
              <q-icon name="medication" />
            </q-item-section>
            <q-item-section>
              <q-item-label class="text-h6">Farmacias</q-item-label>
            </q-item-section>
          </q-item>

          <q-item
            clickable
            v-ripple
            active-class="my-menu-link"
            href="https://www.loxasoluciones-cloud.com:8081/#/login?redirect=/"
          >
            <q-item-section avatar>
              <q-icon name="receipt" />
            </q-item-section>
            <q-item-section>
              <q-item-label class="text-h6">Descargar Factura</q-item-label>
            </q-item-section>
          </q-item>

          <q-item
            clickable
            v-ripple
            active-class="my-menu-link"
            href="https://www.apromedloja.com/webmail/"
          >
            <q-item-section avatar>
              <q-icon name="mail" />
            </q-item-section>
            <q-item-section>
              <q-item-label class="text-h6">Correo Institucional</q-item-label>
            </q-item-section>
          </q-item>

          <q-item
            clickable
            v-ripple
            active-class="my-menu-link"
            href="https://apromedfarmaloja-cloud.com:3020/#/login"
          >
            <q-item-section avatar>
              <q-icon name="schedule" />
            </q-item-section>
            <q-item-section>
              <q-item-label class="text-h6">Gestión Nómina</q-item-label>
            </q-item-section>
          </q-item>

          <q-item clickable v-ripple active-class="my-menu-link">
            <q-expansion-item
              expand-separator
              icon="folder"
              label="Documentos"
              class="text-h6"
            >
              <q-list>
                <q-item clickable v-close-popup>
                  <q-item-section>
                    <q-item-label
                      class="text-subtitle1"
                      clickable
                      @click="onButtonClick(1)"
                    >
                      Clientes de Apromed</q-item-label
                    >
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup>
                  <q-item-section>
                    <q-item-label
                      class="text-subtitle1"
                      clickable
                      @click="onButtonClick(2)"
                      >Usuarios de Apromed</q-item-label
                    >
                  </q-item-section>
                </q-item>
              </q-list>
            </q-expansion-item>
          </q-item>

          <q-item clickable v-ripple active-class="my-menu-link">
            <q-expansion-item
              expand-separator
              icon="description"
              label="Reclamos"
              class="text-h6"
            >
              <q-list>
                <q-item clickable v-close-popup>
                  <q-item-section>
                    <q-item-label
                      class="text-subtitle1"
                      clickable
                      @click="onItemClick(1)"
                    >
                      Clientes de Apromed</q-item-label
                    >
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup>
                  <q-item-section>
                    <q-item-label
                      class="text-subtitle1"
                      clickable
                      @click="onItemClick(2)"
                      >Usuarios de Apromed</q-item-label
                    >
                  </q-item-section>
                </q-item>
              </q-list>
            </q-expansion-item>
          </q-item>
        </q-list>
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router';
import { useAuthStore } from '../stores/auth';
import { DarkMode } from '../components/models';
import { onBeforeMount, ref, watch } from 'vue';
import { LocalStorage, useQuasar } from 'quasar';

// Data
const $q = useQuasar();
const router = useRouter();
const darkMode = ref(false);
const { dark } = useQuasar();
const authStore = useAuthStore();
const rightDrawerOpen = ref(false);
$q.screen.setSizes({ sm: 300, md: 500, lg: 1000, xl: 2000 });

const toggleRightDrawer = () => {
  rightDrawerOpen.value = !rightDrawerOpen.value;
};

const onItemClick = (num: number) => {
  // Redirige a la URL cuando se hace clic en el elemento
  if (num == 1) {
    window.location.href = 'https://apromedreclamos.netlify.app/#/login/1';
  }
  if (num == 2) {
    window.location.href = 'https://apromedreclamos.netlify.app/#/login/2';
  }
};

const onButtonClick = (num: number) => {
  // Redirige a la URL cuando se hace clic en el elemento
  if (num == 1) {
    window.location.href = 'https://apromedreclamos.netlify.app/#/login/4';
  }
  if (num == 2) {
    window.location.href = 'https://apromedreclamos.netlify.app/#/login/3';
  }
};

const redirectTo = (scrollFunction: () => void) => {
  // Redirige a la ruta "/"
  router.push('/');

  // Espera un breve retraso antes de ejecutar scrollToQuienesSomos
  setTimeout(() => {
    scrollFunction();
  }, 100); // Puedes ajustar el tiempo de espera según tus necesidades
};

const scrollToQuienesSomos = () => {
  // Utiliza JavaScript para desplazarte al elemento con el id "quienesSomos"
  const quienesSomosElement = document.getElementById('quienesSomos');
  if (quienesSomosElement) {
    quienesSomosElement.scrollIntoView({ behavior: 'smooth' });
  }
};

const scrollToContacto = () => {
  // Utiliza JavaScript para desplazarte al elemento con el id "quienesSomos"
  const quienesSomosElement = document.getElementById('contacto');
  if (quienesSomosElement) {
    quienesSomosElement.scrollIntoView({ behavior: 'smooth' });
  }
};

watch(
  () => dark.isActive,
  (val) => {
    authStore.setDarkMode(val);
    // Guardar el estado de dark.isActive en el LocalStorage
    LocalStorage.set('darkMode', { darkMode: val });
  }
);

onBeforeMount(async () => {
  const session: DarkMode | null = LocalStorage.getItem('darkMode');
  darkMode.value = session?.darkMode || false;
  if (session?.darkMode !== null) {
    dark.set(darkMode.value);
  }
});
</script>

<style lang="scss" scoped>
.hover-color {
  color: white;
  transition: color 0.3s;

  &:hover {
    color: #ff8000;
  }
}
.text-white a {
  color: inherit; /* Utiliza el color heredado del texto circundante */
  text-decoration: none; /* Elimina la subrayado del enlace si lo hay */
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
