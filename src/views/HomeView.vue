<script setup>
import principal from '../components/principal.vue'
import abajo from '../components/abajo.vue'
</script>

<template>
  <main class="mainn">
    <principal/>
    <img src="../assets/gii.gif" class="imagenn w-64 h-1/2" style="margin: 30px 30px 30px 0px">
  </main>

  <aside class="asidee">
    <abajo/>
  </aside>

</template>

<style>
  .mainn{
  background-image: url("../assets/fondoo.jpg");
   background-size: cover;
   padding: 50px;
   display: inline-flex;
}
.asidee{
  background-image: url("../assets/morty.png");
  background-size: cover;
  padding: 50px;
}
.imagenn{


}
</style>