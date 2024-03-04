<template>
  <div id="catalogCards">
    <h1>{{ flower.name }}</h1>
    <img :src="flower.image" alt="">
    <div id="catalogCards-content">
      <h2 id="catalogCards-content-price"> Cost for each: ${{ flower.price }}</h2>
      <button @click="$emit('addItem', props.flower);">Add to Cart</button>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  flower: Object,
});



</script>

<style scoped>
#catalogCards {
  align-items: center;
  margin-top: 1rem;
  background-color: #bff1ff;
  height: 42rem;
  width: 32rem;
  text-align: center;

}

#catalogCards-content {
  display: flex;
  margin-top: 1rem;
}

h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
  margin-top: 1rem;
}

h2 {
  font-size: 18px;
  margin-top: 1rem;
  margin-right: 1rem;
  margin-left: 1rem;

}

img {
  width: 32rem;
  height: 30rem
}

button {
  background-color: white;
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
}</style>