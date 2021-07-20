<template>
  <div>
    <div class="flex justify-between text-sm text-gray-600 mb-1">
      <span>{{ leftLabel }}</span>
      <span>{{ rightLabel }}</span>
    </div>
    <div class="h-4 bg-indigo-200 relative rounded-lg">
      <span class="inline-block absolute bg-indigo-800 h-full" style="width: 14px" :style="{ left: percent + '%'}"></span>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Slider',
  props: {
    leftLabel: {
      type: String,
      required: true
    },
    rightLabel: {
      type: String,
      required: true
    },
    percent: {
      type: Number,
      required: true
    }
  }
})
</script>

<style scoped>
</style>
