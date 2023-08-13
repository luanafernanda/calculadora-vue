import Calculadora from './components/Calculadora.vue'

<template>
  <div id="app">
    <Calculadora />
  </div>
</template>

<script>

export default {
  components: {
    Calculadora
  }
}
</script>

<style>
  body {
    background-color: #D1C4E9;
  }

  #app {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 90vh;
  }
</style>
