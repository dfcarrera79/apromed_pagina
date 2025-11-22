<template>
  <q-btn
    v-if="showButton"
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
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';

const showButton = ref(false);

const handleScroll = () => {
  showButton.value = window.scrollY > 200;
};

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style lang="scss" scoped>
.scroll-to-top-button {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 1000;
}
</style>
