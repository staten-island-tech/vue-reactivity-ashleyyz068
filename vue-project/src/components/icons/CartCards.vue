<template>
<div>
    
    <h1>{{ props.flower.name }}</h1>
    <img :src="flower.image" alt="">
    <button @click="$emit('removeFromCart')">Remove From Cart</button>
    <h2 >{{ quantity }}</h2>
  </div>
    
</template>

<script setup>
import { defineProps, ref } from "vue";

const props = defineProps({
  flower: Object,
  quantity: Number,
});


// function remove() {
//   clicked.value--;
//   emit("removeFromCart");
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
#cartContainer{
    background-color: black; 
}
h2{
    font-size: 5rem;
}

</style>