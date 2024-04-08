<script setup>
import { ref } from "vue";

const nome = ref('');
const email = ref('');
const senha = ref('');
const confirmarSenha = ref('');
const nascimento = ref('');
const endereco = ref('');
const cidade = ref('');
const hobbies = ref('');
const biografia = ref('');

const mostrarResultado = ref(false)

</script>

<template>
    <h1>Projeto 1</h1>
    <div class="container">
        <div class="formulario">
            <form @submit.prevent="mostrarResultado = !mostrarResultado"></form>
        </div>
    </div>
</template>
