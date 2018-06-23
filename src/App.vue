<template>
  <div id="app">
    
    <DocBuffCalculator/>
  </div>
</template>

<script>
import DocBuffCalculator from "./components/DocBuffCalculator.vue";

export default {
  name: "App",
  components: {
    DocBuffCalculator
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
