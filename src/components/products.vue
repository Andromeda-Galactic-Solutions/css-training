<template>
  <main>
    <h1>Products: Toy Cars</h1>
    <ul>
      <li class="l-grid card">
        <dl class="card-info">
          <dt>Make:</dt> <dd>My make asdlkfjas ;alksdjf ;aksjdjf asdfaklsdjf;asdf ;kasdfj ;ak;jkasdfj</dd>
          <dt>Model:</dt> <dd>My model</dd>
          <dt>Year:</dt> <dd>year</dd>
          <dt>Color:</dt> <dd>color</dd>
          <dt>Price:</dt> <dd>$12.00</dd>
        </dl>
        <button type="button">Buy Now</button>
      </li>
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
ul {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.l-grid {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 1rem;
  width: 15rem;
  padding: 1rem;
}
dl {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 10px;
}
dd { margin: 0; }

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
