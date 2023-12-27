<template>

  <div id="app">
    <h1>Aulas de Vue.js</h1>
    
    <!-- É possível passar variáveis para um componente em sua criação -->
    <!-- Também é possível passar um objeto contendo os atributos relacionados ao objeto-->
    <clientItem :client="client"/>

    <!-- <clientItem :nome="meuNome" :email="meuEmail" :idade="minhaIdade"/> -->

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
      meuNome: "João Henrique",
      meuEmail: "joaohenriquerc123@gmail.com",
      minhaIdade: "22",
      client: {
        nome: "Chico Linguiça",
        email: "chico.linguaca@gmail.com",
        idade: 88
      }
    }
  },

  mounted() {
    document.title = 'Aulas Vue.js';
  },
}
</script>

<style>
</style>
