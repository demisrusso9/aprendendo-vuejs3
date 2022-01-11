<template>
  <section class="dark">
    <div class="flex flex-col h-full bg-white dark:bg-gray-600 p-4 gap-4">
      <input
        class="border-2 border-gray-300 text-center bg-transparent text-white p-2"
        type="text"
        v-model="search"
      />

      <button class="rounded-md p-2 bg-purple-400 cursor-pointer" @click="toggleTheme">
        Theme
      </button>

      <div class="grid grid-cols-3 transition-all">
        <div v-for="(person, i) in filterWord()" :key="person.id">
          <div
            class="flex justify-between border-2 border-gray-500 shadow-lg rounded-md m-1 p-1 text-gray-400"
          >
            <strong class="text-black">[{{ i }}] - </strong>
            <span>
              {{ person.name }}
            </span>
          </div>
        </div>
      </div>

      <p class="text-white">{{ search }}</p>
    </div>
  </section>
</template>

<script lang="ts" setup>
  import { ref } from 'vue'
  import data from '@/assets/data.json'

  const search = ref('')

  function filterWord() {
    return data.filter((item) => item.name.toLocaleLowerCase().startsWith(search.value))
  }

  function toggleTheme() {}
</script>
