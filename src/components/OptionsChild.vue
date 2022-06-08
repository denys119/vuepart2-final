<template>
  <div>
    <h1>
      Options Child component
    </h1>
    <p>
      Message from my parent OptionsApi {{ message }}
    </p>
    <p>
      Number from my parent OptionsApi {{ number }}
    </p>
    <button @click="$emit('myFirstEmit', { name: 'Denis', age: 20 })">
      Click me to trigger a custom event
    </button>
  </div>
</template>

<script>
export default {
  name: 'OptionsChild',
  props: {
    message: String,
    number: Number,
  },
  emits: ['myFirstEmit']
}
</script>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>