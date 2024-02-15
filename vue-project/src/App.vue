<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="https://t4.ftcdn.net/jpg/00/40/47/77/360_F_40477758_of1BAl2mmtekJWsobEnfrMvdN58FqXrU.jpg" />

    <div class="wrapper">
      

      <nav>
        <RouterLink to="/">home</RouterLink>
        <RouterLink to="/Create">about</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  font-size: 20rem;
}
</style>