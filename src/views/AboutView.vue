<script setup>
import personajes from "../components/personajes.vue";
</script>

<template>

<main class="mani">
  <div>
    <h1>Personajes De Rick & Morty</h1>
    <personajes/>
  </div>
</main>



</template>

<style>
.mani{
  background-image: url("../assets/fondoo.jpg");
   background-size: cover;
   display: inline-flex;
}

</style>
