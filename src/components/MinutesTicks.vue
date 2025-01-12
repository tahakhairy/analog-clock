<script setup lang="ts">
const minuteTicks = Array.from({ length: 60 }, (_, i) => i * 6)
</script>

<template>
  <div
    v-for="tick in minuteTicks"
    :key="tick"
    class="w-1 h-1 rounded-full bg-black absolute"
    :class="{ 'w-2 h-2': tick % 5 === 0 }"
    :style="{ transform: `rotate(${tick}deg) translateY(-190px)` }"
  ></div>
</template>

<style scoped></style>
