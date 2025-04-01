<template>
    <h1>Ingresar</h1>

    {{ credenciales }}
    <div>
        <label for="">Ingrese su correo :</label>
        <input type="email" v-model="credenciales.email">
        <strong>{{ errors.email }}</strong>
        <br>
        <label for="">Ingrese su Contraseña :</label>
        <input type="password" v-model="credenciales.password">
        <strong>{{ errors.password }}</strong>
        <br>

        <button @click="ingresar()">INGRESAR</button>
    </div>

    {{ datos }}
</template>

<script setup>
import {ref} from "vue";
import authService from "./../../services/auth.service";

import {useRouter} from "vue-router";

const credenciales = ref ({email: "", password: ""});
const datos = ref(null);
const errors = ref ({})

const router = useRouter()

async function ingresar() {

    try {
        const { data } = await authService.login(credenciales.value);

        localStorage.setItem("access_token", data.access_token)


        router.push("/admin/Perfil")
        //alert(data.access_token)
    } catch (error) {
        console.log(error);
        if (error.status === 401) {
            //alert("error de credenciales") 
        }else{
            errors.value = error.response.data.errors
        }
       // alert("Error al autenticar")

    }
}

</script>