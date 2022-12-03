<template>
  <div id="app">
    <FunComponent/>
  </div>
</template>

<script>
import FunComponent from '@/components/FunComponent.vue';

export default {
  name: 'App',
  components: {
    FunComponent,
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
}
</style>
