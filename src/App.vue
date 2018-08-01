<template>
  <div id="app">
    <parent-component></parent-component>
  </div>
</template>

<script>
import ParentComponent from './components/Parent.vue';

export default {
  name: 'app',
  components: {
    ParentComponent,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
