<template>
  <div id="app">
    <Calculadora />
  </div>
</template>


<script>
  import Calculadora from './components/Calculadora.vue'
  export default {
    components: {
      Calculadora
    }
  }
</script>

<style>



  body {
    background-color: #D1C4E9;
    overflow-y: hidden;
  }

  #app {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
</style>
