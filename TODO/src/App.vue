<script setup>
import { ref } from 'vue';

let nombre = ref('')
let apellido= ref('')
let edad = ref('')
let numero = ref('')
let totalEdad = 0
let pasAño = 1000*60*60*24*365
let años = 0

function calEdad () {

  const edadActual = new Date ()
  let timeAge = new Date (edad.value)

  totalEdad = edadActual- timeAge
  años = parseInt(totalEdad / pasAño)
  return años


}



</script>

<template>
  <section class="padre">
    <div class="tittle"><h1>LOS EVENTOS DE ATENEA</h1></div>

<div class="contenido">
<input v-model="nombre" type="text" placeholder="Ingrese sus nombre">
<input v-model="apellido" type="text" placeholder="Ingrese sus apellidos">
<input v-model="edad" type="date" placeholder="Ingrese su fecha de nacimiento">
<input v-model="numero" type="phone" placeholder="Ingrese su numero de telefono">


</div>

  </section>

  <section class="madre">
    <div class="tittle2"><h1>CONFIRMACION DE DATOS</h1></div>
    <div class="tabla">
      <div class="nombre "><h1>{{ nombre }} {{ apellido }}</h1></div>
      <div class="edad"><h1>{{ calEdad(edad)}}</h1> <h1 v-if="(años<18)"> necesita acompañante</h1></div>
      <div class="numero"><h1>{{ numero }}</h1></div>

      
    </div>





  </section>







</template>

<style scoped>

.tittle{
  background-color: crimson;
  padding: 12px;
  display: flex;
  justify-content: center;
}
.padre{
  background-color: rgb(15, 15, 15);
}
.contenido{
  background-color: aquamarine;
  display: grid;
  margin:  20px auto;
  max-width: 500px;
}
input{
  padding: 15px;
}

.tittle2{
  background-color: crimson;
  padding: 12px;
  display: flex;
  justify-content: center;

}
.madre{
  
  background-color: black;
  display: grid;
  margin:  0px auto;
  max-width: 500px;
  color: aliceblue;
}

</style>
