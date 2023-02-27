<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'

</script>

<template>
  <header class="headerr">
    <div class="barra">
      <img alt="Vue logo" class="logo hover:-translate-y-1 hover:scale-110 duration-300" src="@/assets/rick.png" width="125" height="125" />
      <div class="wrapper">
        <nav class="cont">
          <RouterLink to="/"><p class="text-xl text-white hover:-translate-y-1 hover:scale-110 duration-300 hover:text-cyan-900">Principal</p></RouterLink>
          <RouterLink to="/about"><p class="text-xl text-white hover:-translate-y-1 hover:scale-110 duration-300 hover:text-cyan-900">Personajes</p></RouterLink>
          <RouterLink to=""><p class="text-xl text-white hover:-translate-y-1 hover:scale-110 duration-300 hover:text-cyan-900">Acerca</p></RouterLink>
        </nav>
      </div>
    </div>
  </header>

  <RouterView/>
  
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}
.barra{
  display: inline-flex;
}

.cont{
  margin-top: 30px;
  display: inline-flex;
}
.headerr {
  background-image: url("https://imgs.search.brave.com/G4WKKA4wJ2aEgiSPSbDvWw_4EFm3oxtCzoiT9RlnG1g/rs:fit:1200:646:1/g:ce/aHR0cHM6Ly93YWxs/cGFwZXJhY2Nlc3Mu/Y29tL2Z1bGwvMzk2/MzE5Ni5qcGc");
   background-size: cover;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
