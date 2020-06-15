<template>
  <section class="cart light-blue">
    <h2>Cart</h2>
    <table>
      <thead>
        <tr class="row light-blue header">
          <th class="cell">Make</th>
          <th class="cell">Model</th>
          <th class="cell">Year</th>
          <th class="cell">Color</th>
          <th class="cell number">Price</th>
        </tr>
      </thead>
      <tbody>
        <tr class="row light-blue" v-for="product in products" :key="product.id">
          <td class="cell">{{ product.make }}</td>
          <td class="cell">{{ product.model }}</td>
          <td class="cell">{{ product.year }}</td>
          <td class="cell">{{ product.color }}</td>
          <td class="cell number">${{ product.price }}</td>
        </tr>
      </tbody>
    </table>
    
  </section>
</template>

<style scoped lang="scss">
.row.header > .cell {
  padding: 0.5rem 2rem;
}

</style>

<script>
  import json from '../assets/data/cart-items.json'
  export default {
    name: 'Cart',
    data() { return { products: json }}
  }
</script>
