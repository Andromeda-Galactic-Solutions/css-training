<template>
  <div>
    <h2>Cart</h2>
    <ul id="cart" role="status" aria-atomic="false" aria-live="polite" aria-relevant="additions removals">
      <li v-for="product in products" :key="product.id">
        <div>{{product.year}} {{product.make}} {{product.model}}</div>
        <div>${{product.price}}</div>
      </li>
    </ul>

    <!-- <table>
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
          <td name="Make">{{ product.make }}</td>
          <td name="Model">{{ product.model }}</td>
          <td name="Year">{{ product.year }}</td>
          <td name="Color">{{ product.color }}</td>
          <td name="Price">${{ product.price }}</td>
        </tr>
      </tbody>
    </table> -->
  </div>
</template>

<style scoped lang="scss">
/** List Example **/
ul {
  margin: 0;
  padding: 0;
}
li {
  list-style-type: none;
  padding: 1ex 1ch;
}
li:nth-of-type(even) {
  background: rgba(1, 150, 123, 0.05);
}
li :last-child {
  text-align: right;
}

/** Table Example **/

thead {
  position: absolute;
  left: -9999rem;
}
table, tbody, tr, td {
  display: block;
  width: 100%;
}
td { padding: 1ex 1ch; }
td::before {
  content: attr(name) ': ';
}
tr:nth-of-type(even) td {
  background: rgba(1, 150, 123, 0.05);
}

@media(min-width: 1000px) {
  table {
    display: table;
    table-layout: fixed;
    width: 100%;
    border-collapse: Collapse;
  }
  thead {
    position: relative;
    left: 0;
  }
  tbody { display: table-row-group; }
  tr { display: table-row; }
  td, th {
    padding: 2ex 2ch;
  }
  td {
    display: table-cell;
    font-size: 0.875rem;
  }
  td::before {
    content: ''
  }
}
</style>

<script>
import json from "../assets/data/cart-items.json";
export default {
  name: "Cart",
  data() {
    return { products: json };
  }
};
</script>
