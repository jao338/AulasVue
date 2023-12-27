<template>

    <!-- Usa-se os dois pontos antes de uma propriedade para indicar que o valor dessa propriedade é uma variável -->
    <!-- O nome desse conceito é "one to way data binding", onde os dados são utilizados apenas para visualização -->
    <div id="cliente">
        <div>
            <label for="name">Nome</label>
            <input type="text" name="name" :value="nome">
        </div>
        
        <hr>

        <div>
            <label for="number">Número</label>
            <input type="text" name="number" value="numero">
        </div>
        
        <hr>
    </div>

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