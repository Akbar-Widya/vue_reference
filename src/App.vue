<script setup>
import { ref, computed } from 'vue'

const titleClass = ref('title')
let id = 0
const ProductClothes = ref([
  {id: id++, name: "shirt", price: 10},
  {id: id++, name: "blouse", price: 13},
  {id: id++, name: "gown", price: 16},
  {id: id++, name: "jeans", price: 15},
])

const expensiveItems = computed(() => {
  return ProductClothes.value.filter((product) => product.price >= 15)
})

if (expensiveItems.value.length > 0) {
  // If there are expensive items, set the class to gold
  titleClass.value = 'title-gold'
} 
</script>

<template>
  <h1 :class="titleClass">Product List</h1>
  <ul>
    <li v-for="product in ProductClothes" :key="product.id">
      {{product.name + ': $' + product.price}}
    </li>
  </ul>
</template>

<style>
.title {
  color: purple;
}
.title-gold {
  color: gold;
}
</style>