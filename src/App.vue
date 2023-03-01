
<script setup>
  import {ref} from 'vue'; //para reactivar las variables 
  const name='vue dinamico';
  const stylecolor="color:blue";
  const arrayColores=[{
  "fruta": "verde",
  "tipo": "minivan",
  "capacidad": 7
},{
  "color": "amarillo",
  "tipo": "minivan",
  "capacidad": 7
},{
  "color": "rojo",
  "tipo": "minivan",
  "capacidad": 7
}];
  const activo=false;
  
  //metodos
  const handlerclick=()=>{
    console.log("me diste click cv")
  }
  const handlerclick1=(mensaje)=>{
    console.log(mensaje)
  }
  const contador=ref(0);
  const increment= ()=>{
    contador.value++;//se llama el atributo value para que pueda cambai rla variable ya impresa
  }

 
</script>

<template>
  <h1>{{ name.toUpperCase() }}</h1><!--sirve para llamar una variable--><!--tambien acepta funciones de js-->
  <h2>{{ arrayColores }}</h2>
  <h2 :style="`color: ${arrayColores[2]}`">soy azul</h2> <!--el v-bind es igual a : sirve para llamar una varible en los atributos de la etiqueta-->
  <h2>{{ activo ? "chevere":"barro" }}</h2><!--si es verdadero chevere si no barro-->
  <h2 v-if="activo===true">estoy activo</h2>
  <p v-else-if="activo===false">estoy inactivo</p>
  <p v-else>estoy indeciso</p>
  <p v-show="activo"> display none e caso de que no se cumpla la condicion</p>

<ul>

  <li v-for="(color, index) in arrayColores">
   
    {{ index }}-{{ color }}
  </li>
</ul>

<button v-on:click.right="handlerclick">activame</button>
<button @:click.left="handlerclick1('hola')"> hola mundo</button>

<button @click="increment"> mis pequeños actores</button>

<h2 >{{contador }}</h2>




</template>

<style>
  h1{
    color:red;
  }
</style>