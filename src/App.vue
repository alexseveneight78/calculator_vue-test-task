<template>
  <div class="app">
    <app-calculator></app-calculator>
  </div>
</template>

<script>
  import Calculator from './components/Calculator'
  export default {
    components: {
      appCalculator: Calculator
    }
  }
</script>

<style>
  .app {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
</style>
