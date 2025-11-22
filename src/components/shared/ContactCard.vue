<template>
  <q-card
    class="contact-card custom-hover-background"
    style="height: 220px; width: 250px"
    @mouseenter="handleMouseEnter"
    @mouseleave="handleMouseLeave"
  >
    <q-card-section>
      <div
        class="column justify-center items-center content-center scale-up-center fadeIn"
      >
        <div>
          <div class="text-h4" style="font-family: 'Bebas Neue'">
            {{ title }}
          </div>
        </div>
        <div class="q-py-md">
          <q-btn
            v-if="customIcon"
            round
            style="background: #ffffff; color: white"
            size="lg"
            :href="href"
            target="_blank"
          >
            <q-avatar>
              <img :src="customIcon" />
            </q-avatar>
            <q-tooltip
              class="bg-grey-8 text-body2"
              :offset="[10, 10]"
            >
              {{ tooltipText }}
            </q-tooltip>
          </q-btn>
          <q-btn
            v-else
            outline
            round
            :color="!isHovered ? 'primary' : 'white'"
            :icon="icon"
            size="lg"
            :href="href"
            :target="href ? '_blank' : undefined"
            @click="handleClick"
          >
            <q-tooltip
              v-if="tooltipText"
              class="bg-grey-8 text-body2"
              :offset="[10, 10]"
            >
              {{ tooltipText }}
            </q-tooltip>
          </q-btn>
        </div>
        <div class="text-subtitle2 text-center">
          {{ info }}
        </div>
      </div>
    </q-card-section>
  </q-card>
</template>

<script setup lang="ts">
import { ref } from 'vue';

interface Props {
  title: string;
  icon?: string;
  info: string;
  href?: string;
  customIcon?: string;
  tooltipText?: string;
  onClick?: () => void;
}

const props = defineProps<Props>();

const isHovered = ref(false);

const handleMouseEnter = () => {
  isHovered.value = true;
};

const handleMouseLeave = () => {
  isHovered.value = false;
};

const handleClick = () => {
  if (props.onClick) {
    props.onClick();
  }
};
</script>

<style lang="scss" scoped>
.contact-card {
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out,
    opacity 0.3s ease-in-out;
  border-radius: 10px;

  &:hover {
    transform: translateY(-10px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
    opacity: 0.9;
  }
}

.custom-hover-background {
  &:hover {
    background-color: #ff991b;
    transition: background-color 0.3s;
  }
}

.fadeIn {
  animation: fadeIn 1s ease-in-out;
  animation-fill-mode: forwards;
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
</style>
