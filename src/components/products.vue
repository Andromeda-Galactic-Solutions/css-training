<template>
  <main>
    <h1>Products: Toy Cars</h1>
    <ul>
      <li v-for="product in products" :key="product.id">
        <!-- <h2 :id="'h2_'+product.id">{{product.year }} {{ product.make }} {{ product.model }}</h2> -->
        <dl :id="'dl_'+product.id">
          <dt>Make:</dt> <dd>{{ product.make }} </dd>
          <dt>Model:</dt> <dd>{{ product.model }} </dd>
          <dt>Year:</dt> <dd>{{ product.year }} </dd>
          <dt>Color:</dt> <dd>{{ product.color }} </dd>
          <dt>Price:</dt> <dd>${{ product.price }} </dd>
        </dl>
        <button 
          type="button"
          aria-controls="cart"
          :aria-label="product.year+' '+product.make+' '+product.model"
          
          :aria-details="'dl_'+product.id"
        >Buy Now</button>
      </li>
    </ul>
  </main>
</template>

<style scoped lang="scss">
ul {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
li {
  flex-basis: 200px;
  list-style-type: none;
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
}
dd {
  grid-column: 2 / 5;
}
</style>

<script>
  import json from '../assets/data/products.json'
  export default {
    name: 'Products',
    data() { return { products: json }}
  }
</script>
