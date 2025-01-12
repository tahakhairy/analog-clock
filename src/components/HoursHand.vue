<template>
  
  <div
    class="w-5 md:w-8 h-0 bg-red-600 rounded-full absolute"
    :style="{ transform: `rotate(${180 + hoursHandPosition}deg)` }"
  >
    <img
      class="rotate-180 absolute -top-3 select-none"
      src="/src/assets/images/hourshand.png"
      alt="hours-hand-img"
    />
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  time: Date
  minutes: number
}>()

const hours = computed(() => props.time.getHours() % 12)

const hoursHandPosition = computed(() => hours.value * 30 + props.minutes * 0.5)
</script>

<style scoped></style>
