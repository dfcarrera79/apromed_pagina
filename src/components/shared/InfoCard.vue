<template>
  <q-card
    class="info-card custom-hover-background"
    :style="{ height: height, width: width }"
    @mouseenter="handleMouseEnter"
    @mouseleave="handleMouseLeave"
  >
    <q-card-section>
      <div
        class="column justify-center items-center content-center scale-up-center fadeIn"
      >
        <div class="text-center font-bold q-pt-xl">
          <q-btn
            v-if="number"
            outline
            round
            :color="!isHovered ? 'primary' : 'white'"
            size="lg"
          >
            <strong>{{ number }}</strong>
          </q-btn>
          <q-btn
            v-else-if="icon"
            outline
            round
            :color="!isHovered ? 'primary' : 'white'"
            :icon="icon"
            size="lg"
          />
          <h4 class="q-my-md">
            <strong>{{ title }}</strong>
          </h4>
        </div>
        <div
          :class="
            !isHovered
              ? 'text-subtitle1 text-center'
              : 'text-subtitle1 text-center text-white'
          "
        >
          <p>{{ content }}</p>
        </div>
      </div>
    </q-card-section>
  </q-card>
</template>

<script setup lang="ts">
import { ref } from 'vue';

interface Props {
  title: string;
  content: string;
  icon?: string;
  number?: number;
  height?: string;
  width?: string;
}

const props = withDefaults(defineProps<Props>(), {
  height: 'auto',
  width: '100%',
});

const isHovered = ref(false);

const handleMouseEnter = () => {
  isHovered.value = true;
};

const handleMouseLeave = () => {
  isHovered.value = false;
};
</script>

<style lang="scss" scoped>
.info-card {
  width: 100%;
  max-width: 350px;
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 153, 27, 0.2);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  border-radius: 16px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);

  &:hover {
    transform: translateY(-10px) scale(1.02);
    box-shadow: 0 12px 24px rgba(255, 153, 27, 0.3);
    background: linear-gradient(135deg, #ff991b 0%, #ffb84d 100%);
    border-color: rgba(255, 153, 27, 0.5);
  }
}

// Dark mode support
.element-dark .info-card {
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
