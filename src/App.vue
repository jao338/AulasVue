<template>

  <div id="app">
    <h1>Aulas de Vue.js</h1>
    
    <div v-for="client in clients"  :key="client.id">

      <clientItem :client="client"/>
      
    </div>

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
      
      clients: [
        
        {
          id: 1,
          nome: "João Henrique",
          email: "joaohenriquerc123@gmail.com",
          idade: 22
        },
  
        {
          id: 2,
          nome: "Chico Linguiça",
          email: "chico.linguaca@gmail.com",
          idade: 17
        },
  
        {
          id: 3,
          nome: "Ednaldo Pereira",
          email: "ednaldopereira@gmail.com",
          idade: 120
        },
        
      ]

    }
  },

  mounted() {
    document.title = 'Aulas Vue.js';
  },
}
</script>

<style>
</style>
