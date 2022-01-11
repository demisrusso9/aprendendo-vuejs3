<script lang="ts" setup>
  import { defineProps, ref, reactive, watchEffect, watch, computed } from 'vue'

  const data = reactive({
    name: 'Junior'
  })

  const name = ref('Demis')
  const surname = ref('Russo')
  const msg = ref('vai ser gerada pelo watch')
  const count = ref(0)

  const fullName = computed(() => `${name.value} ${surname.value}`)

  // Always Runs on init
  // watchEffect(() => (data.name = 'Demis Russo'))

  // One value
  watch([count], (val) => {
    msg.value = `Contagem ${val}`
  })

  // Two value
  watch([name, surname], (val) => {
    msg.value = `Mudança no nome (${val})`
  })
</script>

<template>
  <div>
    <p>{{ data.name }}</p>
    <p>{{ fullName }}</p>

    <p>Mensagem: {{ msg }}</p>

    <button
      @click="count++"
      class="bg-purple-400 hover:bg-purple-500 transition-colors p-4 rounded-lg shadow-md text-sm text-white"
    >
      Watch 1
    </button>
    <hr class="my-2 w-full h-1 bg-blue-400" />
    <div class="flex flex-col gap-1 my-2 w-1/2">
      <h1 class="text-black text-xl">Watch 2</h1>
      <input class="p-2" type="text" placeholder="name" v-model="name" />
      <input class="p-2" type="text" placeholder="surname" v-model="surname" />
    </div>
  </div>
</template>
