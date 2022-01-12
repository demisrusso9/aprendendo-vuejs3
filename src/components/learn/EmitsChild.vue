<script lang="ts" setup>
  import { ref } from 'vue'

  defineEmits(['change', 'delete', 'information'])

  const inputValue = ref('')
</script>

<template>
  <div class="flex flex-col gap-3">
    <input
      type="text"
      class="p-2 rounded-xl"
      placeholder="Testing Emits"
      v-model="inputValue"
    />

    <button
      class="bg-blue-400 hover:bg-blue-600 transition-colors p-3 text-white rounded-xl shadow-lg cursor-pointer"
      @click="$emit('information', inputValue)"
    >
      Click to emit
    </button>
  </div>
</template>
