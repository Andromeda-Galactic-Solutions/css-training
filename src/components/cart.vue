<template>
  <section>
    <h2>Cart</h2>
    <table>
      <thead>
        <tr>
          <th>Make</th>
          <th>Model</th>
          <th>Year</th>
          <th>Color</th>
          <th>Price</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="product in products" :key="product.id">
          <td>{{ product.make }}</td>
          <td>{{ product.model }}</td>
          <td>{{ product.year }}</td>
          <td>{{ product.color }}</td>
          <td>${{ product.price }}</td>
        </tr>
      </tbody>
    </table>
    
  </section>
</template>

<style scoped lang="scss"></style>

<script>
  import json from '../assets/data/cart-items.json'
  export default {
    name: 'Cart',
    data() { return { products: json }}
  }
</script>
