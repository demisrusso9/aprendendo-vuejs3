<script lang="ts" setup>
  import { defineProps, ref, reactive } from 'vue'
  const width = ref(0)

  function increase() {
    if (width.value >= 100) return
    width.value += 10
  }
</script>

<template>
  <div>
    <div class="relative h-4 bg-gray-300 rounded-lg w-full">
      <div
        class="absolute h-4 bg-blue-400 rounded-lg"
        :style="{ width: `${width}%` }"
      ></div>
    </div>

    <p class="font-thin">
      CSS width: <span class="text-black text-lg">{{ width }} %</span>
    </p>

    <button class="rounded-md bg-blue-400 p-2 w-40" @click="increase">Click</button>
  </div>
</template>
