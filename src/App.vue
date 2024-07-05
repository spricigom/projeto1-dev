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




    <div class="fundo">




        <div class="container">
            <h1>Projeto 1</h1>
            <div class="formulario">
                <form @submit.prevent="mostrarResultado = !mostrarResultado">








                    <div class="card">
                        <div class="card-header">
                            <label for="">Nome:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="usuario.nome">
                            </blockquote>
                        </div>
                    </div>



                    <div class="card">
                        <div class="card-header">
                            <label for="">Idade:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="number" v-model="usuario.idade">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">Email:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="email" v-model="usuario.email">
                            </blockquote>
                        </div>
                    </div>



                    <div class="card">
                        <div class="card-header">
                            <label for="">Senha:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="password" v-model="usuario.senha">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">Data de nascimento:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="date" v-model="usuario.nascimento">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">CEP:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="number" v-model="endereco.CEP">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">Rua:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="endereco.rua">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">Número:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="number" v-model="endereco.numero">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">Bairro:</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="endereco.bairro">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">Estado:</label>
                            <select name="estados" id="estados" v-model.lazy="usuario.estado">
                                <option value="" disabled selected> Selecione um estado</option>
                                <option v-for="(item, index) in usuario.estado" :key="index"> {{ item }}</option>
                            </select>
                        </div>
                        <div class="card-body">

                        </div>
                    </div>

                   

                    <div class="card">
                        <div class="card-header">
                            <label for="">Hobbies</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="diversos.hobbies">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">Linguagem de Programação</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="diversos.linguagem">
                            </blockquote>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <label for="">Biografia</label>
                        </div>
                        <div class="card-body">
                            <blockquote class="blockquote mb-0">
                                <input type="text" v-model="diversos.biografia">
                            </blockquote>
                        </div>
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
        <p>CEP: {{ endereco.CEP }}</p>
        <p>Rua: {{ endereco.rua }}</p>
        <p>Número: {{ endereco.numero }}</p>
        <p>Bairro: {{ endereco.bairro }}</p>
    </div>
</template>
