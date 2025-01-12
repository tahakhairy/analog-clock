<script setup lang="ts">
const hourNumbers = Array.from({ length: 12 }, (_, i) => i + 1)
</script>

<template>
  <div
    v-for="hour in hourNumbers"
    :key="hour"
    class="absolute"
    :style="{
      transform: `rotate(${hour * 30}deg) translate(0, -165px)`
    }"
  >
    <div
      :style="{ transform: `rotate(${-hour * 30}deg)` }"
      class="font-bold text-[42px]"
    >
      {{ hour }}
    </div>
  </div>
</template>

<style scoped></style>
