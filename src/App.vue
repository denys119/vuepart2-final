<template>
  <div>
    <options-api />
    <composition-api />
    <component-a />
    <component-b />
    <!-- <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link> -->
  </div>
  <!-- <router-view /> -->
</template>

<script setup>
import OptionsApi from './components/OptionsApi.vue';
import CompositionApi from './components/CompositionApi.vue';
import ComponentA from './components/ComponentA';
import ComponentB from './components/ComponentB';
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  min-height: 200vh;
}
</style>
