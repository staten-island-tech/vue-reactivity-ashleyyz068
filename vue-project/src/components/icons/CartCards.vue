<template>
    <div id="cartCards">
        <img :src="flower.image" alt="">
        <div id="cartCards-content">
            <h1>{{ flower.name }}</h1>
            <h2>Quanity: {{ quantity }}</h2>
            <h2 id="cartCards-content-price"> Cost for each: ${{ flower.price }}</h2>
            <button @click="$emit('removeItem')">Remove From Cart</button>
        </div>
    </div>
</template>

<script setup>
import { defineProps, ref } from "vue";

const props = defineProps({
    flower: Object,
    quantity: Number,
});

</script>

<style scoped>
#cartCards-content-price {
    margin-bottom: 6rem;
}

#cartCards {
    display: flex;
    background-color: #bff1ff;
}

#cartCards-content {
    margin-left: 2rem;
}

h1 {
    font-size: 3rem;
}

h2 {
    font-size: 2rem;
}

img {
    width: 20rem;
    height: 20rem
}

div {
    margin-top: 1rem;
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
}

#cartContainer {
    background-color: black;
}</style>