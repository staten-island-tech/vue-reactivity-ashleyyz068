<template>
    <header>
      <div class="head">
        <h1 class="mainTitle">Flower shop</h1>
      </div>
      <MainPage/>
    </header>
    
  
    <RouterView />
    <div class="view">
      <RouterView />
    </div>
  
  </template>
  <script>
  import MainPage from './components/icons/MainPage.vue';
  export default {
    name: 'App', 
    components: {
        MainPage
    }
  }
</script>
  <style scoped></style>
  <style>
    .mainTitle{
        font-size: 4rem;
    }
  </style>