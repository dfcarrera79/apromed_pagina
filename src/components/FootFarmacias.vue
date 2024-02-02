<script setup lang="ts"></script>

<template>
  <div class="column background full-width">
    <div
      class="row justify-around items-center content-center"
      style="height: 150px"
    >
      <div class="text-white">
        <div class="text-h4" style="font-family: 'Lato'">Apromed S.A.S.</div>
        <hr />

        <div class="text-subtitle1 et_pb_text_1">
          Tu salud, nuestro compromiso.
        </div>
      </div>
      <div class="row justify-center">
        <div class="q-pa-md">
          <a href="https://www.facebook.com/farmaciasamericana" target="_blank">
            <q-avatar>
              <img src="../assets/facebook_logo.svg" />
            </q-avatar>
            <q-tooltip
              class="bg-grey-8 text-body2"
              transition-show="scale"
              transition-hide="scale"
              anchor="bottom middle"
              self="top middle"
            >
              Nuestro Facebook
            </q-tooltip>
          </a>
        </div>
        <div class="q-pa-md">
          <a href="https://wa.me/593968822033" target="_blank">
            <q-avatar>
              <img src="../assets/whatsapp.svg" />
            </q-avatar>
            <q-tooltip
              class="bg-grey-8 text-body2"
              transition-show="scale"
              transition-hide="scale"
              anchor="bottom middle"
              self="top middle"
            >
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
            <q-tooltip
              class="bg-grey-8 text-body2"
              transition-show="scale"
              transition-hide="scale"
              anchor="bottom middle"
              self="top middle"
            >
              Envíanos un correo electrónico
            </q-tooltip>
          </q-btn>
        </div>
      </div>
    </div>

    <div>
      <div class="row justify-evenly">
        <p class="text-caption text-white et_pb_text_1">
          Copyright &copy; 2024 Apromed S.A.S.
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.et_pb_text_1 {
  line-height: 1.6em;
  font-family: 'Josefin Sans', Helvetica, Arial, Lucida, sans-serif;
  font-weight: 300;
  font-size: 18px;
  line-height: 1.6em;
}
.custom-caption {
  text-align: left !important;
  font-size: 48px !important;
  line-height: 1.1em !important;
  text-transform: uppercase;
  color: #fff;
  font-weight: 400;
  padding: 12px;
  transition: transform 0.7s ease 0.5s;
  transform: translateX(1400px);
  opacity: 0;
}

.background {
  background: linear-gradient(45deg, #333333, #666666);

  /* Establecer un degradado desvanecido hacia abajo */
  background: linear-gradient(to bottom, #333333, #666666);

  /* Añadir una transición suave para el desvanecido */
  transition: background 0.5s ease;
}

hr {
  border: none;
  height: 0.75px;
  background-color: white;
  width: 100%;
}
</style>
