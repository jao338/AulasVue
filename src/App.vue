<template>

  <div id="app">
    <h3>Cadastro: </h3>

    <small id="nomeErro" v-show="deuErro">O nome é inválido, tente novamente</small>

    <input type="text" placeholder="nome" v-model="nomeField"> <br>
    <input type="email" placeholder="email" v-model="emailField"> <br>
    <input type="number" placeholder="idade" v-model="idadeField"> <br>

    <button @click="cadastrarUsuario">Cadastrar</button>

    <hr>
    
    <!-- Sempre que se utilizar um "v-for" é necessário atribuir a diretiva ":key" como identificador único -->
    <div v-for="(client, index) in clients" :key="client.id">

      <h4>{{ index + 1 }}</h4>

      <!-- O elemento pai espera um elemento customizado vindo de um elemento filho -->
      <clientItem :client="client" @meDelete="deletarUsuario($event)"/>
      
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
      deuErro: false,

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

          // Não faz nada caso o campo esteja vazio, com um espáço ou tenha menos que 3 caracteres.
          if(this.nomeField == "" || this.nomeField == " " || this.nomeField.length < 3){
            this.deuErro = true;
          }else{

            //  Adiciona ao array um objeto contendo as informações do input
            this.clients.push({id: Date.now(), nome: this.nomeField, email: this.emailField, idade: this.idadeField});
            this.nomeField = "";
            this.emailField = "";
            this.idadeField = 0;
          
            this.deuErro = false;

          }
      },

      deletarUsuario: function($event){

        //  Recupera o id do evento
        let id = $event.id;

        //  Filtra o array pelo id dos itens que forem diferentes do id do evento. Ou seja, o item que possuir id igual ao evento é excluído do array
        let array = this.clients.filter(client => client.id != id);

        //  Atribui ao array "clients" com os novos valores
        this.clients = array;

      }

    },
  //  Assim que o componente é montado (ou seja, inserido no DOM), o título do documento HTML é configurado
  //  Obs. Sempre que esse componente for utilizado, independentemente da página, o título será alterado para o especificado
  mounted() {
    document.title = 'Aulas Vue.js';
  },

  components: {
    clientItem,
  },

}
</script>

<style>

  #nomeErro{
    color: red;
  }

</style>
