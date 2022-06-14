<template>
  <div>
    <h1>
      Component B
    </h1>
    <p>
      Mouse position is at: {{ x }}, {{ y }}
    </p>
    <p>
      Count from store: {{ store.count }}
    </p>
  </div>
</template>

<script setup>
import { store } from '../store/store';
import { useMouse } from '../composables/useMouse';
const { x, y } = useMouse();
</script>