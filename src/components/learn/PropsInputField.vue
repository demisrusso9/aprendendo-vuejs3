<script lang="ts" setup>
  import { ref, reactive } from 'vue'

  defineProps({
    msg: String
  })
</script>

<template>
  <section>
    <p>{{ msg }}</p>

    <input
      class="bg-gray-400 text-black"
      type="text"
      @input="$emit('update:modelValue', $event.target.value)"
    />

    <!-- Documentation -->

    <!-- By default, v-model on a component uses modelValue as the prop and update:modelValue as the event. We can modify these names passing an argument to v-model: -->
  </section>
</template>
