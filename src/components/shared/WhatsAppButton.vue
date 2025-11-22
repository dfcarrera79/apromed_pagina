<template>
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
      :href="`https://wa.me/${phoneNumber}`"
    >
      <q-avatar>
        <img src="../../assets/whatsapp.svg" />
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
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';

interface Props {
  phoneNumber: string;
}

defineProps<Props>();

const scrolled = ref(false);

const handleScroll = () => {
  scrolled.value = window.scrollY > 0;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style lang="scss" scoped>
.whatsapp-btn {
  margin-right: 15px;
  margin-bottom: 70px;
  transition: transform 0.5s ease;
}

.fixed-whatsapp-btn {
  margin-right: 15px;
  margin-bottom: 70px;
  transform: translateY(40px);
}
</style>
