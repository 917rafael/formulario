<script setup>
import { ref } from 'vue';
import formulario from './components/formulario.vue'
import resultado from './components/resultado.vue'

const usuarios = ref({})
const mostrarResultado = ref(false)

function clone(usuario) {
    // const novoUsuario = { ...usuario };
    usuarios.value = usuario;    
    mostrarResultado.value = true
    }   
</script>

<template>
    <formulario @adicionar="clone" />
    <resultado v-if="mostrarResultado" :usuarios="usuarios" />
</template>

<style scoped>

</style>
