<script lang="ts" setup>
  import { reactive, computed } from 'vue'

  const person = reactive({
    name: 'Demis',
    surname: 'Russo'
  })

  const products = reactive([
    {
      id: 1,
      name: 'Toy car',
      price: 300
    },
    {
      id: 2,
      name: 'Toy car',
      price: 75
    },
    {
      id: 3,
      name: 'Toy car',
      price: 15
    }
  ])

  // Computed
  // All logic can be put into a computed properties
  const totalPrice = computed(() =>
    products.reduce((acc, curr) => (acc += curr.price), 0)
  )

  const fullName = computed(() => `${person.name} ${person.surname}`)
</script>

<template>
  <div class="grid grid-cols-1 gap-2">
    <h1 class="text-center text-xl">Computed</h1>
    <input type="text" v-model="person.name" />

    <div class="bg-gray-50 p-3 rounded-md shadow-md">
      <p class="text-xl">Computed: {{ fullName }}</p>
      <span class="font-thin">{{ person.name }}</span>
      <span class="font-thin">{{ person.surname }}</span>
    </div>

    <div class="bg-gray-50 p-3 rounded-md shadow-md">
      <p>Computed: {{ totalPrice }}</p>
      <p>Expression: {{ products.reduce((acc, curr) => (acc += curr.price), 0) }}</p>
    </div>

    <button
      @click="
        products.push({
          id: products.length,
          name: 'Toy car',
          price: 10
        })
      "
      class="bg-blue-400 p-2 rounded-lg shadow-lg cursor-pointer my-3"
    >
      Click
    </button>
  </div>
</template>
