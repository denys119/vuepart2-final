<template>
  <div class="container">
    <h1>
      Composition API
    </h1>
    <p>
      Number: {{ number }}
    </p>
    <p>
      Message: {{ message }}
    </p>
    <p>
      Disabled button:
      <button :disabled="disabledButton">
        You can't press me
      </button>
    </p>
    <button @click="number++">
      Press me to increment number
    </button>
    <button @click="number--">
      Press me to decrement number
    </button>
    <button @click="increment">
      Press me to increment number
    </button>
    <button @click="decrement">
      Press me to decrement number
    </button>
    <p>
      Reactive name: {{ data.name }}
    </p>
    <p>
      Reactive age: {{ data.age }}
    </p>
    <button @click="incrementAge">
      Press me to increment age
    </button>
    <button @click="decrementAge">
      Press me to decrement age
    </button>
    <button @click="x++">
      Increment X
    </button>
    <input type="text" ref="input" />
    <composition-child @my-first-emit="customEvent" />
    <p>
      Computed: {{ getNumberState }}
    </p>
    <button @click="incrementByValue(5)">
      Increment by value
    </button>
    <button @click="decrementByValue(5)">
      Decrement by value
    </button>
  </div>
</template>

<script setup>
import CompositionChild from './CompositionChild'
import { ref, reactive, computed, watch, onMounted } from 'vue';
const number = ref(0);
const message = ref("Message");
console.log(message);
number.value = 1;
console.log("Composition API");
const disabledButton = ref(true);
const increment = () => {
  number.value++;
}
function decrement() {
  number.value--;
}
const data = reactive({
  name: 'Denis',
  age: 23
});
function incrementAge() {
  data.age++;
}
function decrementAge() {
  data.age--;
}
const incrementByValue = (value) => {
  number.value = number.value + value;
}
function decrementByValue(value) {
  number.value = number.value - value;
}

const getNumberState = computed(() => {
  return number.value > 5 ? 'Number is bigger than 5' : number.value === 5 ? 'Number is equal with 5' : 'Number is less than 5';
})
const x = ref(0);
watch(x, (newX, oldX) => {
  console.log(newX);
  console.log(oldX);
})
const input = ref(null);
onMounted(() => {
  console.log("The component is mounted");
  input.value.focus();
})
function customEvent(data) {
  console.log(data);
}
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  flex-direction: column;
}
button {
  display: block;
  margin-bottom: 10px;
}
</style>