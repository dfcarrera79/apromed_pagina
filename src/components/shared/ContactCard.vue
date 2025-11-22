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
            <q-tooltip class="bg-grey-8 text-body2" :offset="[10, 10]">
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
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 153, 27, 0.2);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  border-radius: 16px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);

  &:hover {
    transform: translateY(-10px) scale(1.05) rotate(2deg);
    box-shadow: 0 12px 24px rgba(255, 153, 27, 0.3);
    background: linear-gradient(135deg, #ff991b 0%, #ffb84d 100%);
    border-color: rgba(255, 153, 27, 0.5);
  }
}

// Dark mode support
.element-dark .contact-card {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 153, 27, 0.3);
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);

  &:hover {
    background: linear-gradient(135deg, #ff991b 0%, #ffb84d 100%);
    box-shadow: 0 12px 24px rgba(255, 153, 27, 0.4),
      0 0 30px rgba(255, 153, 27, 0.2);
    border-color: rgba(255, 153, 27, 0.6);
  }
}

.custom-hover-background {
  position: relative;
  overflow: hidden;

  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(
      90deg,
      transparent,
      rgba(255, 255, 255, 0.2),
      transparent
    );
    transition: left 0.5s;
  }

  &:hover::before {
    left: 100%;
  }
}

.fadeIn {
  animation: fadeIn 1s ease-in-out;
  animation-fill-mode: forwards;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes scale-up-center {
  0% {
    transform: scale(0.8);
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

.scale-up-center {
  animation: scale-up-center 0.6s cubic-bezier(0.34, 1.56, 0.64, 1) both;
  animation-delay: 0.2s;
  opacity: 0;
}
</style>
