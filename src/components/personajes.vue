<script>
import axios from 'axios'

let API_URL = `https://rickandmortyapi.com/api/character`

export default {

  data() {
    return {
      info: [],
      personajes: [],
      search:'',
      cont:2, 
    }
  },

  mounted() {
    axios.get(API_URL)
      .then((response) => {
        this.info = response.data.info;
        this.personajes = response.data.results;
      })
  },

  methods: {
    pag(num) {
      API_URL='https://rickandmortyapi.com/api/character/?page='+num
      console.log(API_URL)
      axios.get(API_URL)
      .then((response) => {
        console.log(response.config)
        this.info = response.data.info;
        this.personajes = response.data.results;
      })
      this.cont++
    }
  },

  methods: {
    buscador(search) {
      API_URL='https://rickandmortyapi.com/api/character/?name='+search
      console.log(API_URL)
      axios.get(API_URL)
      .then((response) => {
        console.log(response.config)
        this.info = response.data.info;
        this.personajes = response.data.results;
      })

    }
  },
}

</script>

<template>

<input type="text" v-model="search" placeholder="search" style="margin: 10px 10px 10px 10px" class="border border-black"> <button @click="search">buscar</button>

<button @click="pag(cont)" class="border border-fuchsia-900" style="margin: 10px 10px 10px 10px">Siguiente</button> 

  <ul>
  <div class="caja w-96 text-white">
    <li v-for="d in personajes">
    <div class="border border-white box" style="margin: 10px 10px 10px 10px">
      <a class="text-xl">id-{{ d.id }}</a>
      <br>
      <div class="textoimagen">
      <img v-bind:src=" d.image " alt="Personajes_Rick_Morty">

      <div class="informacion" style="margin: 10px 10px 10px 10px">
      <a class="text-xl info" style="margin: 10px 10px 10px 10px"><b>{{ d.name }}</b></a>  
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