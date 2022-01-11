<template>
  <div class="container flex flex-col justify-center items-center">
    <hr class="m-4 border-2 border-red-400 w-full" />
    <h1 class="font-bold text-2xl">{{ outsideMsg }}</h1>
    <hr class="my-4 border-2 border-purple-400 w-full" />
    <h1 class="font-bold text-2xl">{{ outsideBind }}</h1>
    <hr class="my-4 border-2 border-green-400 w-full" />
    <h1 class="font-bold text-2xl">{{ insideMsg }}</h1>
    <hr class="my-4 border-2 border-yellow-400 w-full" />
    <h1 class="font-bold text-2xl">{{ insideMsg }}</h1>
    <hr class="my-4 border-2 border-blue-400 w-full" />
    <h1 class="font-bold text-2xl">{{ insideMsg }}</h1>
    <hr class="my-4 border-2 bg-pink-700 w-full" />
    <h1 class="font-bold text-2xl">{{ insideMsg }}</h1>
    <hr class="my-4 border-2 border-red-800 w-full" />
  </div>
</template>

<script lang="ts" setup>
  import { defineProps, ref } from 'vue'

  defineProps({
    outsideMsg: String,
    outsideBind: String
  })

  // Outside props can be binded or unbinded
  // Only use if another component needs to access the props above

  const insideMsg = 'Testing props'
</script>
