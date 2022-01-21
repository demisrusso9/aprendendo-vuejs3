<script lang="ts" setup>
  import { defineProps, ref, reactive } from 'vue'
  import EmitsChild from './EmitsChild.vue'

  /* Emits
    useful for forms and inputs
    emit has 2 arguments
    emit(eventName, payload)
    1 - name of the event of the parent component
    2 - payload is the data to send  (optional)

  */

  function showInformation(event: InputEvent) {
    console.warn(`coming from Component EmitsChild: ${event}`)
  }

  const teste = () => console.log('teste')
</script>

<template>
  <section>
    <EmitsChild @information="showInformation" />
    <!-- <EmitsChild @click="teste" /> -->
    <!-- <EmitsChild @click="showInformation($event.)" /> -->
  </section>
</template>
