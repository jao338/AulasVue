<template>

    <div id="client">
        <h4>Nome: {{ client.nome }}</h4>
        <hr>
        <p>Email: {{ client.email }}</p>
        <p>Idade: {{ client.idade }}</p>

    </div>

</template>

<script>

export default ({
    data(){
        return {
            // nome : "João Henrique",
            // numero: "999955882",
            // email: "joaohenriquerc123@gmail.com",
            // idade: 0,
        }
    },

    props: {
        nome: String,
        email: String,
        idade: Number,
        numero: Number,
        client: Object
    }
})

</script>

<style scoped>

    #client{
        max-width: 256px;
        border: 1px solid black;
        padding: 1%;
        margin-bottom: 32px;
    }

</style>