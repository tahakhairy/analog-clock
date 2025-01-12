<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'
import Clock from './components/Clock.vue'

const time = ref(new Date())

let timer: number

onMounted(() => {
  setInterval(() => {
    time.value = new Date()
    document.title = time.value.toLocaleTimeString()
  }, 1000)
})

onUnmounted(() => {
  clearInterval(timer)
})
</script>

<template>
  <div
    class="h-screen flex justify-center items-center bg-gradient-to-r from-violet-200 to-pink-200"
  >
    <Clock :time />
  </div>
</template>

<style>
@import url(/src/assets/base.css);
</style>
