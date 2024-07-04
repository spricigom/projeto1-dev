<script setup>
import { reactive, ref } from "vue";

const usuario = reactive({
    nome: '',
    email: '',
    idade: 0,
    senha: '',
    nascimento: '',
    estado: ["AC", "AL", "AP", "AM", "BA", "CE", "DF", "ES", "GO", "MA", "MT", "MS", "MG", "PA", "PB", "PR", "PE", "PI", "RJ", "RN", "RS", "RO", "RR", "SC", "SP", "SE", "TO"],

})
const endereco = reactive({
    CEP: '',
    rua: '',
    numero: '',
    bairro: '',
})
const diversos = reactive({
    hobbies: '',
    linguagem: '',
    biografia: ''

})
const mostrarResultado = ref(false)

//if (usuario.idade <= 18 && usuario.idade >= 60) {}
''</script>



<template>

    <div class="container">
        <h1>Projeto 1</h1>
        <div class="formulario">
            <form @submit.prevent="mostrarResultado = !mostrarResultado">
                <div class="row">
                    <label for="">Nome:</label>
                    <input type="text" v-model="usuario.nome">
                </div>
                <div class="row">
                    <label for="">Idade:</label>
                    <input type="number" v-model="usuario.idade">
                </div>
                <div class="row">
                    <label for="">Email:</label>
                    <input type="email" v-model="usuario.email">
                </div>
                <div class="row">
                    <label for="">Senha:</label>
                    <input type="password" v-model="usuario.senha">
                </div>
                <div class="row">
                    <label for="">Data de nascimento:</label>
                    <input type="date" v-model="usuario.nascimento">
                </div>
                <div class="row">
                    <label for="">CEP:</label>
                    <input type="number" v-model="endereco.CEP">
                </div>
                <div class="row">
                    <label for="">Rua:</label>
                    <input type="text" v-model="endereco.rua">
                </div>
                <div class="row">
                    
                    <label for="">Número:</label>
                    <input type="number" v-model="endereco.numero">
                </div>
                <div class="row">
                    <label for="">Bairro:</label>
                    <input type="text" v-model="endereco.bairro">
                </div>
                <div class="row">
                    <label for="">Estado:</label>
                    <select name="estados" id="estados" v-model.lazy="usuario.estado">
                        <option value="" disabled selected> Selecione um estado</option>
                        <option v-for="(item, index) in usuario.estado" :key="index">  {{item}}</option>
                    </select>
                </div>
                <div class="row">
                    <label for="">Hobbies</label>
                    <input type="text" v-model="diversos.hobbies">
                </div>
                <div class="row">
                    <label for="">Linguagem de Programação</label>
                    <input type="text" v-model="diversos.linguagem">
                </div>
                <div class="row">
                    <label for="">Biografia</label>
                    <input type="text" v-model="diversos.biografia">
                </div>
                <button type="submit">Mostrar</button>
            </form>
        </div>
    </div>
    <div v-if="mostrarResultado">
        <h2>Resultado</h2>
        <p>Nome: {{ usuario.nome }}</p>
        <p>Email: {{ usuario.email }}</p>
        <p>Senha: {{ usuario.senha }}</p>
        <p>Data de nascimento: {{usuario.nascimento}}</p>
        <p>CEP: {{ endereco.CEP }}</p>
        <p>Rua: {{ endereco.rua }}</p>
        <p>Número: {{ endereco.numero }}</p>
        <p>Bairro: {{endereco.bairro}}</p>
    </div>
</template>
