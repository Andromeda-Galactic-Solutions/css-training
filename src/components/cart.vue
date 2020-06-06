<template>
  <div>
    <h2>Cart</h2>
    <div class="table-container">
      <table>
        <thead>
          <tr>
            <th>Model</th>
            <th>Make</th>
            <th>Year</th>
            <th>Color</th>
            <th>Price</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="product in products" :key="product.id">
            <td name="Model" :title="product.model">{{ product.model }}</td>
            <td name="Make" :title="product.make">{{ product.make }}</td>
            <td name="Year" :title="product.year">{{ product.year }}</td>
            <td name="Color" :title="product.color">{{ product.color }}</td>
            <td name="Price" :title="product.price">$ {{ product.price }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style scoped lang="scss">
  @use '../assets/scss/mixins.scss' as *;
  @use '../assets/scss/theme.scss' as *;

  .table-container {
    box-shadow: $box-shadow;
  }
  thead {
    position: absolute;
    left: -9999rem;
  }
  th { 
    @extend .label;
    font-weight: 400;
  }
  table, tbody, tr, td {
    display: block;
    width: 100%;
  }
  td { padding: 1ex 1ch; }
  td:before {
    content: attr(name) ": ";
    @extend .label;
  }
  tr:nth-of-type(odd) td {
    background: rgba(1, 150, 123, 0.05);
  }

  @media(min-width: $medium) {
    table {
      display: table;
      table-layout: fixed;
      width: 100%;
      border-collapse: collapse;
      background: white;
    }
    thead { 
      position: relative;
      left: 0;
    }
    tbody { display: table-row-group; }
    tr { display: table-row;}
    td, th {
      text-align: right;
      border-bottom: solid 1px $border-color;
      padding: 2ex 2ch;
      white-space: nowrap;
      text-overflow: ellipsis;
      overflow: hidden;
    }
    td {
      display: table-cell;
      font-size: .875rem;
      &:before {
        content: ''
      }
    }
    td:first-of-type, th:first-of-type {
      text-align: left;
    }
  }
</style>

<script>
  import json from '../assets/data/cart-items.json'
  export default {
    name: 'Cart',
    data() { return { products: json }}
  }
</script>
