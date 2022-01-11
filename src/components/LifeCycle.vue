<template>
  <div>
    <h1 class="m-3 font-bold text-4xl">{{ lifeCycle }}</h1>
    <p>LifeCycle</p>
    <hr />
  </div>
</template>

<script lang="ts">
  import { defineComponent } from 'vue'

  export default defineComponent({
    name: 'LifeCycle',
    data() {
      return {
        lifeCycle: 'ok'
      }
    },
    created() {
      this.lifeCycle = 'Demis Russo'
    },
    mounted() {
      this.lifeCycle = 'Mendes'
    }
  })
</script>
