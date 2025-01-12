<template>
  <div
    class="w-[200px] h-[200px] md:w-[400px] md:h-[400px] bg-blue-200 rounded-full flex justify-center items-center relative border-[4px] ring-8 ring-blue-900 border-black"
  >
    <SecondsHand :time />
    <MinutesHand :time />
    <HoursHand :time :minutes="time.getMinutes()" />

    <HoursNubmers />
    <MinutesTicks />
  </div>
</template>

<script setup lang="ts">
import HoursHand from './HoursHand.vue'
import HoursNubmers from './HoursNubmers.vue'
import MinutesHand from './MinutesHand.vue'
import MinutesTicks from './MinutesTicks.vue'
import SecondsHand from './SecondsHand.vue'

const props = defineProps<{
  time: Date
}>()
</script>

<style scoped></style>
