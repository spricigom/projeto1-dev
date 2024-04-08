<script setup>
import { reactive, ref } from "vue";

const usuario = reactive({
    nome: '';
})

const mostrarResultado = ref(false)

</script>

<template>
    <h1>Projeto 1</h1>
    <div class="container">
        <div class="formulario">
            <form @submit.prevent="mostrarResultado = !mostrarResultado">
                <div class="row">
                    <label for="">Nome:</label>
                    <input type="text" name="" id="">
                </div>
                <div class="row">
                    <label for="">Email:</label>
                    <input type="email" name="" id="">
                </div>
                <div class="row">
                    <label for="">Senha:</label>
                    <input type="password" name="" id="">
                </div>
            </form>
        </div>
        <button type="submit">Mostrar</button>
    </div>
</template>
