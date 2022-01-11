<template>
  <div>
    <h1 class="m-3 font-bold text-4xl">{{ title }}</h1>

    <form action="">
      <label for="">Nome:</label>
      <input type="text" placeholder="Digite teu nome" v-model="inputName" />
    </form>

    <hr />
  </div>
</template>

<script>
  export default {
    name: 'Form',
    data() {
      return {
        title: 'Form',
        name: 'Demis',
        inputName: ''
      }
    }
  }
</script>
