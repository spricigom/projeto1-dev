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

</script>

<template>
    <input type="text" v-model="nome" placeholder="Digite seu nome">
    <p>Nome:</p>
</template>
