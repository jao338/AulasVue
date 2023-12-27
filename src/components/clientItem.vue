<template>

    <!-- Usa-se os dois pontos antes de uma propriedade para indicar que o valor dessa propriedade é uma variável -->
    <!-- O nome desse conceito é "two way data binding", onde os dados não servem apenas para visualização. Sendo que, desta maneira é posível alterar o valor de uma variável dinamicamente e em tempo real -->
    <div>
        <div>
            <label for="name">Nome</label>
            <input type="text" name="name" v-model="nome">
        </div>
        
        <hr>

        <div>
            <label for="number">Número</label>
            <input type="text" name="number" :value="numero">
        </div>
        
        <hr>

        <div>
            <label for="email">Email</label>
            <input type="text" name="email" value="email">
        </div>

    </div>

    <p>A variável nome tem como valor: {{ nome }}</p>

    <p>A variável numero tem como valor: {{ numero }}</p>

    <p>A variável email tem como valor: {{ email }}</p>

</template>

<script>

export default ({
    data(){
        return {
            nome : "João Henrique",
            numero : "999955882",
            email : "joaohenriquerc123@gmail.com",
            idade : 0,
        }
    }
})

</script>

<style scoped>

    #box{
        width: 40px;
        height: 40px;
        background-color: rgb(0, 0, 0);
    }

</style>