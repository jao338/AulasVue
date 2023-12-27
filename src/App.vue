<template>

  <div id="app">
    <h1>Aulas de Vue.js</h1>
    
    <!-- É possível passar variáveis para um componente em sua criação -->
    <!-- Também é possível passar um objeto contendo os atributos relacionados ao objeto-->
    <clientItem :client="client1" :showAge="true"/>
    <clientItem :client="client2" :showAge="true"/>
    <clientItem :client="client3" :showAge="true"/>

  </div>

</template>

<script>
import clientItem from "./components/clientItem";

export default {
  name: 'App',
  components: {
    clientItem,
  },

  data(){
    return{
      
      client1: {
        nome: "João Henrique",
        email: "joaohenriquerc123@gmail.com",
        idade: 22
      },

      client2: {
        nome: "Chico Linguiça",
        email: "chico.linguaca@gmail.com",
        idade: 17
      },

      client3: {
        nome: "Veio",
        email: "veio123@gmail.com",
        idade: 120
      },

    }
  },

  mounted() {
    document.title = 'Aulas Vue.js';
  },
}
</script>

<style>
</style>
