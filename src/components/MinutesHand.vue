<template>
  <div
    class="w-8 h-0 bg-red-600 rounded-full absolute"
    :style="{ transform: `rotate(${180 + minutesHandPosition}deg)` }"
  >
    <img
      class="rotate-180 absolute -top-2"
      src="/src/assets/images/minuteshand.png"
      alt="minutes-hand-img"
    />
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  time: Date
}>()

const minutes = computed(() => props.time.getMinutes())
const minutesHandPosition = computed(() => minutes.value * 6)
</script>

<style scoped></style>
