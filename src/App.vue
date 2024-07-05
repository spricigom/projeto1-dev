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
           

            <div class="card" id="titulo">
                        <div class="card-header">
                             <h1>Projeto 1</h1>
                        </div>
            </div>


            <div class="formulario">
                <form @submit.prevent="enviarDados">

                    <div class="card">
                        <div class="card-header">
                            <label for="">Nome:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="usuario.nome" placeholder="Digite seu nome.">
                            </blockquote>
                        </div>
                    </div>



                   

                    <div class="card">
                        <div class="card-header">
                            <label for="">Email:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="email" v-model="usuario.email" placeholder="Digite seu email.">
                            </blockquote>
                        </div>
                    </div>



                    <div class="card">
                        <div class="card-header">
                            <label for="">Senha:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="password" v-model="usuario.senha" placeholder="Digite sua senha. Ex:Senha123!">
                            </blockquote>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-header">
                            <label for=""> Confirmação de senha:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="password" v-model="usuario.confirmSenha"
                                    placeholder="Digite sua senha novamente.">
                            </blockquote>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-header">
                            <label for="">Data de nascimento:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="date" v-model="usuario.nascimento"
                                    placeholder="Digite sua data de nascimento.">
                            </blockquote>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-header">
                            <label for="">Endereço</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="usuario.endereco" placeholder="Digite seu endereço.">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for=""> Selecione seu estado:</label>
                            <select name="estados" id="estados" v-model.lazy="usuario.estado">
                                <option v-for="(item, index) in estados" :value="item" :key="index"> {{ item }}</option>
                            </select>
                       

                        </div>
                    </div>



                    <div class="card">
                        <div class="card-header">
                            <label for="">Hobbies</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="diversos.hobbies" placeholder="Digite seus hobbies.">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">Linguagem de Programação</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="diversos.linguagem"
                                    placeholder="Digite as linguagens de programação que utiliza.">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">Biografia</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="diversos.biografia" placeholder="Digite sua bigrafia.">
                            </blockquote>
                        </div>
                    </div>
                    <button type="submit" id="botao" class="btn " >Mostrar</button>
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
