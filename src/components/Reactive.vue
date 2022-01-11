<template>
  <div>
    <p class="font-bold">{{ God.name }}</p>
    <p class="font-bold">{{ God.attributes }}</p>

    <input class="border-4 rounded" type="text" v-model="God.inputValue" />

    <button
      class="border rounded-2xl bg-blue-400 p-4 w-44 text-2xl m-4"
      @click="addAttributes(God.inputValue)"
    >
      click
    </button>
  </div>
</template>

<script lang="ts" setup>
  import { reactive } from 'vue'

  const God = reactive({
    name: 'Jesus Cristo',
    attributes: [
      'Immortal',
      'Savior of humanity',
      'omniscience',
      'omnipresence',
      'omnipotent'
    ],
    inputValue: ''
  })

  function addAttributes(text: string) {
    God.attributes.push(text)
  }
</script>
