<template>
  <div>
    <h1>
      Component A
    </h1>
    <p>
      Mouse position is at: {{ x }}, {{ y }}
    </p>
    <p>
      Count from store: {{ store.count }}
    </p>
    <button @click="store.incrementCount">
      Increment the count from store
    </button>
  </div>
</template>

<script setup>
import { useMouse } from '../composables/useMouse';
import { store } from '../store/store';
const { x, y } = useMouse();
</script>