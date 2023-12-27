<template>

  <div id="app">
    <h1>Videos-Aulas de Vue.js</h1>
    <clientItem/>
    <productItem/>
  </div>

</template>

<script>
import clientItem from "./components/clientItem";
// import productItem from "./components/productItem";

export default {
  name: 'App',
  components: {
    clientItem,
    // productItem
  },

  mounted() {
    document.title = 'Aulas Vue.js';
  },
}
</script>

<style>
</style>
