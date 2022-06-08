<template>
  <div>
    <options-api />
  </div>
</template>

<script>
import OptionsApi from './components/OptionsApi.vue';
export default {
  name: 'App',
  components: {
    OptionsApi
  }
}
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
