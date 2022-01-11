<template>
  <div class="h-full flex-col justify-center items-center m-3 p-3 bg-gray-100">
    <div class="grid grid-cols-2 gap-4">
      <Input :modelItem="name" />
      <Input :modelItem="age" />
    </div>

    <button
      class="rounded bg-green-400 p-3 my-6 hover:shadow-xl hover:bg-green-500 transition"
      @click="addNewItem"
    >
      Add item
    </button>

    <hr class="border-2 my-2" />

    <ul class="flex flex-row" v-for="(item, i) in list" :key="i">
      <li class="text-green-300 mr-3">{{ item.id }}</li>
      <li class="text-green-300 mr-3">{{ item.name }}</li>
      <li class="text-green-300 mr-3">{{ item.age }}</li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
  import { ref, defineProps } from 'vue'
  import { Props } from '../../types/TypesProps'
  import Input from '../Input.vue'

  const list = ref([] as Props[])

  const name = ref('')
  const age = ref()

  function addNewItem() {
    console.log(name.value, age.value)

    const item: Props = {
      id: list.value.length,
      name: name.value,
      age: age.value
    }

    list.value.push(item)
  }

  const width = ref(0)

  function increase(value: number) {
    return width.value <= 99 && (width.value += value)
  }
</script>
