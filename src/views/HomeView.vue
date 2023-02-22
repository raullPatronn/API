<script setup>
import principal from '../components/principal.vue'
import abajo from '../components/abajo.vue'
</script>

<template>
  <main class="mainn">

    <div class="aa">
    <principal/>
    </div>

    <img src="../assets/gii.gif" class="imagenn w-64 h-1/2" style="margin: 55px 30px 30px 0px">
  </main>

  <aside class="asidee" >
    <abajo/>
  </aside>
</template>

<style>
  .mainn{
   background-image: url("../assets/fondoo.jpg");
   background-size: cover;
   width: 100%;
   display: inline-flex;
}
.aa{
  padding: 50px;
}

.asidee{
  background-image: url("../assets/morty.png");
  background-size: cover;
  width: 100%;

}
.imagenn{


}
</style>