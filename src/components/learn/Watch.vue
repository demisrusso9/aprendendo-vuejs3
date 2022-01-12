<script lang="ts" setup>
  import { defineProps, ref, reactive, watchEffect, watch, computed } from 'vue'

  const data = reactive({
    name: 'Junior'
  })

  const car = reactive({
    brand: '',
    model: '',
    year: ''
  })

  const msg = ref('Vai ser gerada pelo watchers')
  const fullName = computed(() => `${name.value} ${surname.value}`)

  const name = ref('')
  const surname = ref('')
  const email = ref('')
  const document = ref('')
  const age = ref()
  const count = ref(0)

  // Always Runs on init
  watchEffect(() => {
    msg.value = 'watchEffect'
  })

  // Watching One value
  watch([count], (val) => {
    msg.value = `Watch 1 (count) ${val}`
  })

  // Watching Two value
  watch([name, surname], (val) => {
    msg.value = `Watch 2 (name, surname) (${val})`
  })

  // Watching Three value
  watch([age, email, document], (val) => {
    msg.value = `Watch 3 (age, email, document) (${val})`
  })
</script>

<template>
  <div class="">
    <p><span class="font-semibold mr-1">watchEffect:</span> {{ data.name }}</p>
    <p><span class="font-semibold mr-1">computed:</span> {{ fullName }}</p>
    <p><span class="font-semibold mr-1">Mensagem:</span> {{ msg }}</p>

    <button
      @click="count++"
      class="bg-purple-400 hover:bg-purple-500 transition-colors p-2 mt-4 rounded-lg shadow-md text-sm text-white"
    >
      Watch 1
    </button>

    <hr class="my-2 w-full h-1 bg-blue-400" />

    <div class="flex flex-col my-2 gap-2 mx-auto">
      <section class="flex gap-2">
        <h1>Watch 2</h1>
        <input class="p-1" type="text" placeholder="name" v-model="name" />
        <input class="p-1" type="text" placeholder="surname" v-model="surname" />
      </section>

      <section class="flex gap-2">
        <h1>Watch 3</h1>
        <input class="p-1" type="number" placeholder="age" v-model="age" />
        <input class="p-1" type="email" placeholder="email" v-model="email" />
        <input class="p-1" type="text" placeholder="document" v-model="document" />
      </section>
    </div>
  </div>
</template>
