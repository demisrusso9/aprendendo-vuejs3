<template>
  <div>
    <h1 class="m-3 font-bold text-4xl">{{ text }}</h1>

    <div v-if="working">
      <h1>IF</h1>
      <p>Lista</p>
    </div>

    <div v-else>
      <h1>ELSE</h1>
      <p>Lista</p>
    </div>

    <hr />

    <p v-show="working">{{ msg }}</p>
    <p v-if="working">Teste</p>
    <p v-else>Else</p>
    <a :href="link">Link: google.com</a>

    <!-- <Picture /> -->
    <hr />
    <br />
    <hr />

    <button
      class="rounded bg-green-400 p-3 m-2 hover:shadow-xl hover:bg-green-500 transition"
      @click="showInformation"
    >
      {{ !show ? 'Mostrar informações' : 'Esconder informações' }}
    </button>

    <p v-show="show">Hello there</p>
  </div>
</template>

<script lang="ts">
  import { defineComponent } from 'vue'
  import Picture from './Picture.vue'

  export default defineComponent({
    name: 'Info',
    components: {
      Picture
    },
    props: {
      text: String
    },
    data() {
      return {
        working: true,
        msg: 'I think I understanding',
        link: 'https://google.com',
        show: false
      }
    },
    methods: {
      showInformation() {
        console.log(this.show)
        this.show = !this.show
      }
    }
  })
</script>
