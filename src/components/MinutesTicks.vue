<script setup lang="ts">
import { computed } from 'vue'

const minuteTicks = Array.from({ length: 60 }, (_, i) => i * 6)

const screenWidth = computed(() => window.screen.width)
</script>

<template>
  <div
    v-for="tick in minuteTicks"
    :key="tick"
    class="w-1 h-1 rounded-full bg-black absolute translate"
    :class="{ 'w-2 h-2': tick % 5 === 0 }"
    :style="{
      transform: `rotate(${tick}deg) translateY(${
        screenWidth < 768 ? '-92' : '-190'
      }px)`
    }"
  ></div>
</template>

<style scoped></style>
