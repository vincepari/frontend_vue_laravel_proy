<template>
    <h1>Mi Perfil</h1>

    {{ Perfil }}

    <button @click="funSalir">Salir  (Cerrar Seciones)</button>
</template>

<script setup>

import { onMounted, ref } from 'vue';
import { useRouter } from 'vue-router';
import authService from '../../services/auth.service';

const Perfil = ref({})
const router = useRouter()

onMounted(() => {
    obtenerPerfil()
})

async function obtenerPerfil(){
   const {data} = await authService.profile();
    Perfil.value=data;
}

async function funSalir(){
   const {data} = await authService.logout()
    localStorage.removeItem("access_token");
    router.push("/auth/login");
}
</script>