<template>
  <div>
    <div>Cart</div>
    <div v-for="product in products" :key="product.id">
      <span>Make: {{ product.make }}, </span>
      <span>Model: {{ product.model }}, </span>
      <span>Year: {{ product.year }}, </span>
      <span>Color: {{ product.color }}, </span>
      <span>Price: ${{ product.price }}, </span>
      <span>Posted: {{ product.posted }} </span>
    </div>
  </div>
</template>

<style scoped lang="scss"></style>

<script>
  import json from '../assets/data/cart-items.json'
  export default {
    name: 'Cart',
    data() { return { products: json }}
  }
</script>
