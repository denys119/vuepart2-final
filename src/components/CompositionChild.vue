<template>
  <div>
    <h1>
      Composition API Child Component
    </h1>
    {{ message }}
    <button @click="emit('myFirstEmit', { name: 'Denis', age: 23 })">
      Click me to trigger a custom event
    </button>
  </div>
</template>

<script setup>
import { defineProps, defineEmits, inject } from 'vue';
const props = defineProps({
  message: String,
});
const emit = defineEmits(["myFirstEmit"]);
console.log(props);
const providedNumber = inject('providedNumber');
console.log(providedNumber.value);
</script>

<style scoped>
</style>