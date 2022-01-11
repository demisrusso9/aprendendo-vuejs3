<template>
  <div>
    <hr class="border-2 w-full my-4" />

    <form
      class="flex flex-col m-4 bg-gray-300 border-4 border-gray-600"
      @submit.prevent="handleSubmit"
    >
      <section class="grid grid-cols-2">
        <div class="flex flex-row flex-1 justify-center items-center">
          <label class="text-center text-purple-600 mr-4" for="id">Id</label>
          <input
            class="p-2 my-3 rounded-md"
            type="text"
            name="id"
            placeholder="Enter your id"
            required
          />
        </div>

        <div class="flex flex-row justify-center items-center">
          <label class="text-center text-purple-600 mr-4" for="name">Name</label>
          <input
            class="p-2 my-3 rounded-md"
            type="text"
            name="name"
            placeholder="Enter your name"
            required
          />
        </div>

        <div class="flex flex-row justify-center items-center">
          <label class="text-center text-purple-600 mr-4" for="age">Age</label>
          <input
            class="p-2 my-3 rounded-md"
            type="text"
            name="age"
            placeholder="Enter your age"
            required
          />
        </div>

        <div class="flex flex-row justify-center items-center">
          <label class="text-center text-purple-600 mr-4" for="email">Email</label>
          <input
            class="p-2 my-3 rounded-md"
            type="email"
            name="email"
            placeholder="Enter your email"
            required
          />
        </div>
      </section>

      <button
        type="submit"
        class="rounded p-2 m-3 text-center bg-purple-400 hover:bg-purple-700 text-white transition-colors"
      >
        Enviar
      </button>
    </form>

    <div class="grid grid-cols-4">
      <p class="text-center text-purple-500">
        <strong class="font-bold">Id:</strong> {{ formId }}
      </p>
      <p class="text-center text-purple-500">
        <strong class="font-bold">Name:</strong> {{ formName }}
      </p>
      <p class="text-center text-purple-500">
        <strong class="font-bold">Age</strong> {{ formAge }}
      </p>
      <p class="text-center text-purple-500">
        <strong class="font-bold">Email</strong> {{ formEmail }}
      </p>
    </div>

    <button @click="showMessage">Clica ae</button>
  </div>
</template>

<script lang="ts" setup>
  import { ref } from 'vue'

  const formId = ref('')
  const formName = ref('')
  const formAge = ref('')
  const formEmail = ref('')

  function handleSubmit(e: Event) {
    // const { id, name, age, email } = Object.fromEntries(new FormData(e.target))
    // formId.value = id.toString()
    // formName.value = name.toString()
    // formAge.value = age.toString()
    // formEmail.value = email.toString()
  }

  function showMessage() {
    console.log('Jesus Christ our Lord')
  }
</script>
