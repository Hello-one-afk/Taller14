<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App" />


  <AgregarNombre nombre="LUIS" apellido="perez"> </AgregarNombre>

  <div id="container-datos">
    <label for="">Ingrese nombre </label>
    <input id="npt" v-model="nombre" placeholder="Nombre...">
    <label for="">Ingrese Apellido </label>
    <input id="npt" v-model="apellido" placeholder="Apellido...">
    <button id="btn" @click="agregarLista()">Enviar</button>
  </div>

  <MostrarLista></MostrarLista>
  <div id="container-mostrar-lista">
    <ul>
      <li v-for="(nombreCompleto, index) in listaNombre" :key="index">
        <span> {{ "Numero: " + index + " | Nombre: " + nombreCompleto }}</span>
        <div id="container-btn">
          <button id="btn" class="editar" @click="editarDatos(index)">Editar </button>
          <button id="btn" class="eliminar" @click="eliminarDatos(index)">Eliminar</button>
  
        </div>
        </li>
    </ul>
  </div>




</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import AgregarNombre from './components/AgregarNombre.vue'
import MostrarLista from './components/MostrarLista.vue';
import { ref } from 'vue'
export default {
  name: 'App',
  components: {
    HelloWorld,
    AgregarNombre,
    MostrarLista,
  },
  data() {
    return {
      nombre: ref(''),
      apedillo: ref(''),
      listaNombre: ref([]),
    }
  },
  methods: {
    agregarLista() {
      this.listaNombre.push(this.nombre + " " + this.apedillo);

    },
    editarDatos(index) {
      console.log("editar Dato numero " + index);
    },
    eliminarDatos(index) {
      this.listaNombre.splice(index, 1);
    },

  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#btn {

  border: none;
  color: rgb(255, 255, 255);
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 10px;
  background-color: rgb(168, 168, 168);
  border: 3px solid #000000;
  margin-right: 1.5%;
  margin-top: 2%;
  margin-bottom: 2%;
}

#btn:hover {
  background: #f00e0eb4;
  color: rgb(0, 0, 0);
}


#container-mostrar-lista{
background: rgb(143, 110, 98);
border-radius: 10px;
color: white;

}
</style>
