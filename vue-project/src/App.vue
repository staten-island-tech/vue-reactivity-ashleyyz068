<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <h1>
      Kristy's Flowers
    </h1>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  text-align: center;
  height:40rem;
  font-size: 20rem;
  background-position: center;
  background-image: url(https://img.freepik.com/free-vector/hand-painted-watercolor-pastel-sky-background_23-2148902771.jpg?w=1800&t=st=1709510504~exp=1709511104~hmac=f484b2e982917d5badf1b8fcc5f0515f45e448aaf09eb9326e36316a33dd169a) ;
}
h1{
  padding-top: 10rem;
}
</style>