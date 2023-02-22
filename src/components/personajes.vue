<script>
import axios from 'axios'

let API_URL = `https://rickandmortyapi.com/api/character`

export default {

  data() {
    return {
      info: [],
      personajes: [],
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

}

</script>

<template>

  <input type="text" v-model="search" placeholder="search" style="margin: 10px 10px 10px 10px" class="border border-black">


  <button @click="pag(cont)" class="border border-fuchsia-900" style="margin: 10px 10px 10px 10px">Siguiente</button> 

  <ul>
  <div class="caja w-96">
    <li v-for="p in personajes">

    <div class="border border-black box" style="margin: 10px 10px 10px 10px">
      <a>id-{{ p.id }}</a>
      <br>
      <img v-bind:src=" p.image " alt="">
      <br>
      <a>{{ p.name }}</a>  
    </div>
    </li>
  </div>

  </ul>


</template>
<style>
  .caja{
    display: inline-block;
  }
  .box{
    padding: 20px;
  }
</style>