<script setup>
import personajes from "../components/personajes.vue";
</script>

<template>

<main class="mani">
    <br>
    <h1 class="text-white text-2xl" style="margin: 10px 10px 10px 10px">Personajes De <a class="hover:text-cyan-400">Rick</a> & <a class="hover:text-amber-400">Morty</a></h1>
    <personajes/>

</main>

<footer>

</footer>

</template>

<style>
.mani{
  background-image: url("../assets/fondoo.png");
   background-size: cover;


}


</style>
