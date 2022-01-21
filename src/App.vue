<script lang="ts" setup>
  import Array from './components/Array.vue'
  import CompositionAPI from './components/learn/CompositionAPI.vue'
  import Computed from './components/learn/Computed.vue'
  import ExperienceBar from './components/ExperienceBar.vue'
  import Form from './components/Form.vue'
  import Info from './components/Info.vue'
  import LifeCycle from './components/LifeCycle.vue'
  import ListVfor from './components/ListVfor.vue'
  import Picture from './components/Picture.vue'
  import Reactive from './components/Reactive.vue'
  import TestingProps from './components/TestingProps.vue'
  import Watch from './components/learn/Watch.vue'
  import Emits from './components/learn/Emits.vue'
  import PropsInputField from './components/learn/PropsInputField.vue'
  import { ref } from 'vue'

  const name = ref('Demis Russo')
  const input = ref('')
</script>

<template>
  <main
    class="bg-gray-800 text-gray-200 h-screen flex flex-col flex-1 items-center justify-center p-3 mx-auto"
  >
    <p>name: {{ name }}</p>
    <p>input: {{ input }}</p>

    <PropsInputField msg="Hello World" v-model="input" />
  </main>
</template>
