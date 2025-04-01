<template>
  <h1>Mi Componenete Principal (APP:vue)</h1>
  <h2>
    Menu de navegacion
  </h2>

  <RouterLink to="/">INICIO</RouterLink>|
  <RouterLink to="/Nosotros">NOSOTROS</RouterLink>|
  <RouterLink to="/servicios">SERVICIOS</RouterLink>|
  <RouterLink to="/auth/login">INGRESAR</RouterLink>

  <hr>
  <RouterView />
</template>