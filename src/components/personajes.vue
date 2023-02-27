<script type="text/javascript">
  
import axios from 'axios'

let API_URL = `https://rickandmortyapi.com/api/character`

export default {

  data() {
    return {
      info: [],
      personajes: [],
      current:1,
      pages: 20,
      buscar:'',
    };
  },

  mounted() {
    axios.get(API_URL)
      .then((response) => {
        this.info = response.data.info;
        this.personajes = response.data.results;

      })

  },
methods: {
    buscador(buscar) {
      API_URL='https://rickandmortyapi.com/api/character/?name='+buscar
      axios.get(API_URL)
      .then((response) => {
        this.info = response.data.info;
        this.personajes = response.data.results;
      })

    },
    navpag(num) {
      API_URL='https://rickandmortyapi.com/api/character/?page='+this.pagina
      axios.get(API_URL)
      .then((response) => {
        this.info = response.data.info;
        this.personajes = response.data.results;
      })

    },

  }

  


}


</script>

<template>

<input type="text" v-model="buscar" placeholder="Escribir Nombre" style="margin: 10px 10px 10px 10px" class="border border-white">
<button @click="buscador(buscar)" class="boton bg-blue-400 text-orange-800"><b>Buscar</b></button>

 

  <ul>
  <div class="caja w-96 text-white">
    <li v-for="d in personajes">
    <div class="border border-white box" style="margin: 10px 10px 10px 10px">
      <a class="text-xl">id-{{ d.id }}</a>
      <br>
      <div class="textoimagen">

      <img v-bind:src=" d.image " alt="Personajes_Rick_Morty">

      <div class="informacion" style="margin: 10px 10px 10px 10px">
      <a class="text-xl info hover:text-orange-600" style="margin: 10px 10px 10px 10px"><b>{{ d.name }}</b></a>  
      <a class="text-xl info" style="margin: 10px 10px 10px 10px">Género: {{ d.gender }}</a>
      <a class="text-xl info" style="margin: 10px 10px 10px 10px">Especie: {{ d.species }}</a>
      <a class="text-xl info" style="margin: 10px 10px 10px 10px">Estado: {{ d.status }}</a>
      </div>
      </div>
    </div>
    </li>
  </div>
  </ul>
</template>
<style>
  .boton{
    padding: 5px;
    border-radius:50%;
  }
  .textoimagen{
    display: inline-flex;
  }
  .info{
    display: block;
  }
  .informacion{
    float: right;
  }
  .caja{
    display: inline;
  }
  .box{
    padding: 20px;
  }
</style>