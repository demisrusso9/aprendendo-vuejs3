<template>
  <input class="rounded bg-gray-100 p-2 shadow-lg" type="text" />
</template>

<script lang="ts" setup>
  import { defineProps } from 'vue'

  defineProps({
    modelItem: String
  })
</script>
