<template>
    <div id="page">
        <div id="page-catalog">
            <FlowerCard v-for="flower in flowers" :key="flower.name" :flower="flower" @addItem="addItem(flower)" />
        </div>

        <div id="page-cart">
            <CartCard v-for="(item, index) in cartItems" :key="index" :flower="item.flower" :quantity="item.quantity"
                @removeItem="removeItem(index)" />
            <div>
                <p>Total Price: ${{ totalPrice.toFixed(2) }}</p>
            </div>
        </div>
    </div>
</template>

<script setup>

import FlowerCard from "@/components/icons/FlowerCard.vue";
import CartCard from "@/components/icons/CartCards.vue";
import { ref, computed } from "vue";

const cartItems = ref([]);

function addItem(flower) {

    const existingCartItem = cartItems.value.find(
        (item) => item.flower.name === flower.name
    );

    if (existingCartItem) {
        existingCartItem.quantity++;
    } else {
        cartItems.value.push({ flower, quantity: 1 });
    }
}

function removeItem(index) {
    if (cartItems.value[index].quantity > 1) {
        cartItems.value[index].quantity--;
    } else {
        cartItems.value.splice(index, 1)
    }
}

const totalPrice = computed(() => {
    return cartItems.value.reduce((total, item) => {
        return total + parseFloat(item.flower.price) * item.quantity;
    }, 0);
});

const flowers = [
    {
        name: 'Bloomsy Roses',
        price: '69.99',
        image: 'https://www.datocms-assets.com/32926/1684509106-2_bb1116-18_pandora-roses_lifestyle.jpg?w=900h%3D1200&auto=format&fit=max&q=75'
    },
    {
        name: 'Be My Valentine',
        price: '35.99',
        image: 'https://www.datocms-assets.com/32926/1698955386-1_bb896-22_be-my-valentine_hands.jpg?w=900h%3D1200&auto=format&fit=max&q=75'
    },
    {
        name: 'Red Velvetier',
        price: '44.99',
        image: 'https://www.datocms-assets.com/32926/1692205726-1_bb774-35_red-velvetier_hands.jpg?w=900h%3D1200&auto=format&fit=max&q=75'
    },
    {
        name: 'Velvet Blush',
        price: '48.99',
        image: 'https://www.datocms-assets.com/32926/1698943516-1_bb887-28_velvet-blush_hands.jpg?w=900h%3D1200&auto=format&fit=max&q=75'
    },
    {
        name: 'Pink Cupcake',
        price: '59.99',
        image: 'https://www.datocms-assets.com/32926/1704380651-1_bb186-44_pink-cupcake-premium_front.jpg?h=1000&w=800&crop=focalpoint&fit=crop&fp-x=0.4&auto=format&q=75'
    },
    {
        name: 'Bloomsy Original',
        price: '59.99 ',
        image: 'https://www.datocms-assets.com/32926/1690492100-2_bb979-26_garden-fresh_lifestyle.jpg?h=1000&w=800&crop=focalpoint&fit=crop&fp-x=0.4&auto=format&q=75'
    },
    {
        name: 'Celebration',
        price: '64.99',
        image: 'https://www.datocms-assets.com/32926/1687967185-1_bb125-29_celebration_hands.jpg?h=1000&w=800&crop=focalpoint&fit=crop&fp-x=0.4&auto=format&q=75'
    },
    {
        name: 'Purple Peony Tulips',
        price: '79.99',
        image: 'https://www.datocms-assets.com/32926/1683550429-1_bb710-30_purple-peony-tulips_hands.jpg?h=1000&w=800&crop=focalpoint&fit=crop&fp-x=0.4&auto=format&q=75'
    },
    {
        name: 'Pink Peony Tulips',
        price: '99.99',
        image: 'https://www.datocms-assets.com/32926/1696344545-1_bb719-50_pink-peony-tulips_hands.jpg?h=1000&w=800&crop=focalpoint&fit=crop&fp-x=0.4&auto=format&q=75'
    },
    {
        name: 'Cupids Bow',
        price: '74.99',
        image: 'https://www.datocms-assets.com/32926/1704380865-1_bb892-25_spring-is-in-the-air_hands.jpg?h=1000&w=800&crop=focalpoint&fit=crop&fp-x=0.4&auto=format&q=75'
    },
    {
        name: 'Sweet Tulips',
        price: '64.99',
        image: 'https://www.datocms-assets.com/32926/1686575005-1_bb662-25_sweet-spring_hands.jpg?h=1000&w=800&crop=focalpoint&fit=crop&fp-x=0.4&auto=format&q=75'
    },
];

</script>

<style scoped>
h1 {
    color: aqua;
}

#page {
    background-color: #fcd7d4;
    padding-bottom: 4rem;
}

#page-catalog {
    width: 70vw;
    flex-wrap: wrap;
    display: flex;
    justify-content: space-around;

}

#page-cart {
    width: 29vw;
    margin-left: 1vw;
}

#page {
    font-family: 'Archivo', sans-serif;
    display: flex;
}
p{
    font-size: 3rem;
}
</style>
