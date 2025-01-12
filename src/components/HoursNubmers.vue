<script setup lang="ts">
import { computed } from 'vue'

const hourNumbers = Array.from({ length: 12 }, (_, i) => i + 1)

const screenWidth = computed(() => window.screen.width)
</script>

<template>
  <div
    v-for="hour in hourNumbers"
    :key="hour"
    class="absolute"
    :style="{
      transform: `rotate(${hour * 30}deg) translateY(${
        screenWidth < 768 ? '-75' : '-165'
      }px)`
    }"
  >
    <div
      :style="{ transform: `rotate(${-hour * 30}deg)` }"
      class="font-bold text-lg md:text-[42px]"
    >
      {{ hour }}
    </div>
  </div>
</template>

<style scoped></style>
