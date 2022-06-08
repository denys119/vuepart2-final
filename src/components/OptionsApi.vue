<template>
  <div class="container">
    <h1>
      Options API
    </h1>
    <p>
      Number from data state: {{ number }}
    </p>
    <p>
      Number from data state: {{ message }}
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
      Press me to increment number using methods
    </button>
    <button @click="decrement">
      Press me to decrement number using methods
    </button>
    <p>
      Computed property: {{ getNumberState }}
    </p>
    <p>
      X from data state: {{ x }}
    </p>
    <button @click="x++">
      Increment x
    </button>
    <p>
      Ref input
    </p>
    <input type="text" ref="input">
    <options-child message="Hello" :number="number" @my-first-emit="emitEvent" />
  </div>
</template>

<script>
import OptionsChild from './OptionsChild.vue';
export default {
  name: 'OptionsApi',
  components: {
    OptionsChild
  },
  data () {
    return {
      number: 1,
      message: 'Hello World',
      disabledButton: true,
      x: 1
    }
  },
  methods: {
    increment() {
      this.number++;
    },
    decrement() {
      this.number--;
    },
    emitEvent(data) {
      console.log(data);
    }
  },
  computed: {
    getNumberState() {
      return this.number > 5 ? 'Number is bigger than 5' : this.number === 5 ? 'Number is equal than 5' : 'Number is less than 5';
    }
  },
  watch: {
    x(newX, oldX) {
      console.log("old x was", oldX);
      console.log("new x is", newX);
    }
  },
  mounted() {
    console.log(`the component is now mounted.`);
    this.$refs.input.focus();
  },
  created() {
    console.log('the component is now created');
  },
  unmounted() {
    console.log('component is now unmounted');
  },
  beforeUnmount() {
    console.log(`component before unmount`);
  }
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