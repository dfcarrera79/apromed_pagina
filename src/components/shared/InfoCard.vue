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
