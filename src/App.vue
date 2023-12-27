<template>

  <div id="app">
    <h3>Cadastro: </h3>

    <input type="text" placeholder="nome" v-model="nomeField"> <br>
    <input type="email" placeholder="email" v-model="emailField"> <br>
    <input type="number" placeholder="idade" v-model="idadeField"> <br>

    <button @click="cadastrarUsuario">Cadastrar</button>

    <hr>
    
    <div v-for="(client, index) in clients"  :key="client.id">

      <h4>{{ index + 1 }}</h4>
      <clientItem :client="client"/>
      
    </div>

  </div>

</template>

<script>
import clientItem from "./components/clientItem";

export default {
  name: 'App',

  data(){
    return{
    
      nomeField: "",
      emailField: "",
      idadeField: 0,

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

        {
          id: 4,
          nome: "Ricardo Milos",
          email: "ricardo.milos@gmail.com",
          idade: 40
        },
        
      ],

    }
  },

    methods: {
        cadastrarUsuario: function(){

        this.clients.push({id: Date.now(), nome: this.nomeField, email: this.emailField, idade: this.idadeField});

        this.nomeField = "";
        this.emailField = "";
        this.idadeField = 0;

      }
    },

  mounted() {
    document.title = 'Aulas Vue.js';
  },

  components: {
    clientItem,
  },

}
</script>

<style>
</style>
