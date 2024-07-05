<script setup>
import { reactive, ref } from "vue";

const estados = ["AC", "AL", "AP", "AM", "BA", "CE", "DF", "ES", "GO", "MA", "MT", "MS", "MG", "PA", "PB", "PR", "PE", "PI", "RJ", "RN", "RS", "RO", "RR", "SC", "SP", "SE", "TO"]

const usuario = reactive({
    nome: '',
    email: '',
    senha: '',
    confirmSenha: '',
    nascimento: '',
    endereco: ''
})

const diversos = reactive({
    hobbies: '',
    linguagem: '',
    biografia: ''

})
const mostrarResultado = ref(false)

function enviarDados() {
    let error = false
    if (usuario.nome == '') {
        alert("Faltou o nome")
        error = true
    }
    if (usuario.email == '') {
        alert("Faltou o email")
        error = true
    }
    if (usuario.senha == '') {
        alert("Faltou a senha")
        error = true
    }
    if (usuario.confirmSenha == '') {
        alert("Faltou a confirmação de senha")
        error = true
    }
    if (usuario.senha !== usuario.confirmSenha) {
        alert("Senhas não conferem")
        error = true
    }
    if (usuario.nascimento == '') {
        alert("Faltou a data de nascimento")
        error = true
    }
    if (usuario.endereco == '') {
        alert("Faltou o endereço")
        error = true
    }
    if (diversos.hobbies == '') {
        alert("Faltou o hobbies")
        error = true
    }
    if (diversos.linguagem == '') {
        alert("Faltou a linguagem de programção")
        error = true
    }
    if (diversos.biografia == '') {
        alert("Faltou a sua biografia")
        error = true
    }
    if (estados == '') {
        alert("Faltou o estado")
        error = true
    }
    // validar
    if (!error) {
        mostrarResultado.value = !mostrarResultado.value
    }
}
</script>



<template>
    <div class="fundo">

        <div class="container">
            <h1>Projeto 1</h1>
            <div class="formulario">
                <form @submit.prevent="enviarDados">
                    <div class="row">
                        <label for="">Nome:</label>
                        <input type="text" v-model="usuario.nome" placeholder="Digite seu nome.">
                    </div>
                    <div class="row">
                        <label for="">Email:</label>
                        <input type="email" v-model="usuario.email" placeholder="Digite seu email.">
                    </div>
                    <div class="row">
                        <label for="">Senha:</label>
                        <input type="password" v-model="usuario.senha" placeholder="Digite sua senha. Ex:Senha123!">
                    </div>
                    <div class="row">
                        <label for="">Confirmação de senha:</label>
                        <input type="password" v-model="usuario.confirmSenha" placeholder="Digite sua senha novamente.">
                    </div>
                    <div class="row">
                        <label for="">Data de nascimento:</label>
                        <input type="date" v-model="usuario.nascimento" placeholder="Digite sua data de nascimento.">
                    </div>
                    <div class="row">
                        <label for="">Endereço:</label>
                        <input type="text" v-model="usuario.endereco" placeholder="Digite seu endereço.">
                    </div>
                    <div class="row">
                        <label for=""> Selecione seu estado:</label>
                        <select name="estados" id="estados" v-model.lazy="usuario.estado">
                            <option v-for="(item, index) in estados" :value="item" :key="index"> {{ item }}</option>
                        </select>
                    </div>
                    <div class="row">
                        <label for="">Hobbies:</label>
                        <input type="text" v-model="diversos.hobbies" placeholder="Digite seus hobbies.">
                    </div>
                    <div class="row">
                        <label for="">Linguagem de Programação:</label>
                        <input type="text" v-model="diversos.linguagem"
                            placeholder="Digite as linguagens de programação que utiliza.">
                    </div>
                    <div class="row">
                        <label for="">Biografia:</label>
                        <input type="text" v-model="diversos.biografia" placeholder="Digite sua bigrafia.">
                    </div>
                    <button type="submit" id="botao">Mostrar</button>
                </form>
            </div>
        </div>
    </div>
    <div v-if="mostrarResultado">
        <h2>Resultado</h2>
        <p>Nome: {{ usuario.nome }}</p>
        <p>Email: {{ usuario.email }}</p>
        <p>Senha: {{ usuario.senha }}</p>
        <p>Data de nascimento: {{ usuario.nascimento }}</p>
        <p>Endereço: {{ usuario.endereco }}</p>
        <p>Estado: {{ estados }}</p>
        <p>Hobbies: {{ diversos.hobbies }}</p>
        <p>Linguagem de programação: {{ diversos.linguagem }}</p>
        <p>Biografia: {{ diversos.biografia }}</p>
    </div>
</template>
