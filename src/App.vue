<script setup>
import Calculator from './components/Calculator.vue';
</script>

<template>
  <div id="app">
    <h1>Calculadora Simples em Vue</h1>
    <Calculator />
  </div>
</template>

<style scoped>
#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 90vh;
  text-align: center;
  font-family: 'Courier New', Courier, monospace;
  margin-top: 20px;
}

h1 {
  text-shadow: 2px 2px 2px red, -2px -2px 2px blue;
}
</style>
