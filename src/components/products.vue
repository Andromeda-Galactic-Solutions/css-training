<template>
  <main>
    <h1>Products: Toy Cars</h1>
    <ul>
      <li v-for="product in products" :key="product.id">
        <img src="../assets/img/toy-car.jpg" alt="toy car">
        <dl>
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
  @use '../assets/scss/theme.scss' as theme;
  @use '../assets/scss/mixins.scss' as *;

  ul { 
    padding-left: 0; 
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
  }
  li {
    flex-basis: 200px;
    list-style-type: none; 
    box-shadow: $box-shadow;
    margin: 1rem;
    padding: 0 10px;
    background: white;
  }
  dl {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 1ch;
  }
  dt {
    grid-column: 1;
    @extend .label;
  }
  dd {
    grid-column: 2 / 5;
  }
  button {
    display: block;
    width: 75%;
    margin: 2ex auto;
    padding: 1.25ex 2ch;
  }
  img {
    width:100%;
    max-width: 640px;
    height: auto;
  }

</style>

<script>
  import json from '../assets/data/products.json'
  export default {
    name: 'Products',
    data() { return { products: json }}
  }
</script>
