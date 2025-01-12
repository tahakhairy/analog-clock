<template>
  <div
    class="w-8 h-8 bg-black rounded-full absolute flex justify-center items-center z-10"
    :style="{ transform: `rotate(${180 + secondsHandPosition}deg)` }"
  >
    <div class="clock-hand h-[120px] bg-red-600"></div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  time: Date
}>()

const seconds = computed(() => props.time.getSeconds())
const secondsHandPosition = computed(() => seconds.value * 6)
</script>

<style scoped>
.clock-hand {
  position: absolute;
  width: 6px; /* Adjust thickness */
  top: 50%;
  transform-origin: top;
  border-radius: 5px; /* Rounded edges for the hands */
}
</style>
