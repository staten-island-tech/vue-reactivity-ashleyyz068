<template>
    <div>
      <h1>{{ Flower.name }}</h1>
      <img :src="Flower.image" alt="">
      <h2>{{ clicked }}</h2>
      <button @click="increment">Add to Cart</button>
    </div>
  </template>

<script setup>
// import {ref} from "vue";

const props = defineProps({
    Flower: Object, 
})

// const clicked =ref(0);
// function increment(){
//     clicked.value++;
// }

</script>

<style scoped>
h1{
    font-size: 5rem;
}
img{
    width: 20rem;
    height: 20rem

}
div{
    margin-top: 1rem;
    background-color: aqua;
}
button{
  background-color: rgba(51, 51, 51, 0.05);
  border-radius: 8px;
  border-width: 0;
  color: #333333;
  cursor: pointer;
  display: inline-block;
  font-family: "Haas Grot Text R Web", "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 14px;
  font-weight: 500;
  line-height: 20px;
  list-style: none;
  margin: 0;
  padding: 10px 12px;
  text-align: center;
  transition: all 200ms;
  vertical-align: baseline;
  white-space: nowrap;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}
h2{
    font-size: 5rem;
}
</style>