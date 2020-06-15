<template>
  <main>
    <h1>Products: Toy Cars</h1>
    <ul>
      <li class="l-grid card" v-for="product in products" :key="product.id">
        <dl class="card-info">
          <dt>Make:</dt> <dd>{{ product.make }}</dd>
          <dt>Model:</dt> <dd>{{ product.model }}</dd>
          <dt>Year:</dt> <dd>{{ product.year }}</dd>
          <dt>Color:</dt> <dd>{{ product.color }}</dd>
          <dt>Price:</dt> <dd>${{ product.price }}</dd>
        </dl>
        <button type="button">Buy Now</button>
      </li>
    </ul>
  </main>
</template>

<style scoped lang="scss">
// LAYOUT
.l-grid {
  display: inline-block;
  margin: 1rem;
  width: 15rem;
}

// WIDGET / THEME
.card {
  background-color: #edecec;
  text-align: right;
}
.card-info {
  text-align: left;
}
</style>

<script>
  import json from '../assets/data/products.json'
  export default {
    name: 'Products',
    data() { return { products: json }}
  }
</script>
