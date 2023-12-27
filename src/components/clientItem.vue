<template>

    <div :class="{'client': !isPremium, 'client-premium': isPremium}">
        <h4>Nome: {{ client.nome }}</h4>
        <hr>
        <p>Email: {{ client.email }}</p>

        <!-- Caso use "v-if" e "v-else", o elemento é exibido caso a condição seja verdadeira ou destruído caso seja falsa -->
        <!-- O "v-else" deve ser usado após "v-if" e não recebe nenhum parâmetro -->
        <p v-if="showAge">Idade: {{ client.idade }}</p>
        <p v-else>A idade foi ocultada</p>

        <p v-if="client.idade < 18">O cliente é menor de idade</p>
        <p v-else-if="client.idade >= 120">O cliente é velho demais</p>
        <p v-else-if="client.idade >= 18">O cliente é maior de idade</p>
        

        <!-- Ao usar "v-show", o elemento é exibido caso a condição seja verdadeira, mas caso seja falsa o elemento é ocultado -->
        <!-- <p v-show="showAge">Idade: {{ client.idade }}</p> -->

    </div>

</template>

<script>

export default ({
    data(){
        return {
            isPremium: false
        }
    },

    props: {
        client: Object,
        showAge: Boolean
    }
})

</script>

<style scoped>

    .client{
        max-width: 256px;
        border: 1px solid black;
        padding: 1%;
        margin-bottom: 32px;
    }

    .client-premium{
        max-width: 256px;
        background: rgb(75, 75, 75);
        color: yellow;
        padding: 1%;
        margin-bottom: 32px;
    }

</style>