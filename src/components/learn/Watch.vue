<script lang="ts" setup>
  import { defineProps, ref, reactive, watchEffect } from 'vue'

  const data = reactive({
    name: 'Junior'
  })

  // Always Runs on init
  watchEffect(() => (data.name = 'Demis Russo'))
</script>

<template>
  <p>{{ data.name }}</p>
</template>
