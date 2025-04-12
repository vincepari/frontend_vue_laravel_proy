<script setup lang="ts">
import { RouterLink } from 'vue-router';

</script>

<template>


  <RouterLink to="/">INICIO</RouterLink>|
  <RouterLink to="/Nosotros">NOSOTROS</RouterLink>|
  <RouterLink to="/servicios">SERVICIOS</RouterLink>|
  <RouterLink to="/auth/login">INGRESAR</RouterLink>|
  <RouterLink to="/admin/usuario">USUARIOS</RouterLink>

  <hr>
  <RouterView />
</template>