<template>
    <div>
      <h1>{{ Flower.name }}</h1>
    </div>
  </template>

<script>
import {ref} from "vue";

const props = defineProps({
    Flower: Object, 
})
</script>

<style scoped>
</style>