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
@use '../assets/scss/theme' as t;
@use '../assets/scss/mixins' as *;
ul {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
  padding: 0;
}
li {
  @extend .card-defaults;
}
li:first-of-type { 
  @include card(pink);
  transform: scale(.75) translate(250px, 20px);
}
li:nth-of-type(2) { @include card(brown) }

@keyframes spin {
  0% { transform: rotate(0); }
  50% { transform: rotate(360deg); }
  100% { transform: rotate(0); }
}
li:nth-of-type(3) {
  @include card(indigo);
  // animation: spin 1s linear infinite;
}
li:nth-of-type(4) { 
  @include card(violet);
  transition: all 250ms ease-in-out;
  &:hover {
    transform: skew(-25deg);
  }
}

// scale(sx, sy)
// translate(tx, ty)
// rotate(∠)
// skew(∠x, ∠y)


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


button {
  border-radius: 0;
  background: white;
  color: t.$primary;
  padding: t.$default-padding;
  transition: 250ms ease-in;
  &:hover, &:focus {
    border-radius: 25px;
    background: t.$primary;
    color: white;
  }
}
</style>

<script>
  import json from '../assets/data/products.json'
  export default {
    name: 'Products',
    data() { return { products: json }}
  }
</script>
