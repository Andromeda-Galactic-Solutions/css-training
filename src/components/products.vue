<template>
  <div>
    <div>Products: Toy Cars</div>
    <div v-for="product in products" :key="product.id">
      <span>Make: {{ product.make }}, </span>
      <span>Model: {{ product.model }}, </span>
      <span>Year: {{ product.year }}, </span>
      <span>Color: {{ product.color }}, </span>
      <span>Price: ${{ product.price }} </span>
      <div>Buy Now</div>
    </div>
  </div>
</template>

<style scoped lang="scss"></style>

<script>
  import json from '../assets/data/products.json'
  export default {
    name: 'Products',
    data() { return { products: json }}
  }
</script>
