<template>
  <section class="cart light-blue">
    <h2>Cart</h2>
    <div class="table-overflow-container">
      <table>
        <thead>
          <tr class="row light-blue header">
            <th name="Make" class="l cell">Make</th>
            <th class="cell">Model</th>
            <th class="cell">Year</th>
            <th class="cell">Color</th>
            <th class="cell number">Price</th>
          </tr>
        </thead>
        <tbody>
          <tr class="row light-blue" v-for="product in products" :key="product.id">
            <td name="Make" class="cell"> asdlkfalksdfj ;aksdf ;asdkk djkls;k jkda;kd jdklskd kdlskd jfkdlsksldkk kdlaskdfj fjkdlaskdf fjdklskdasjdfskdflasdjf laskdjflsjdflsdkfjas jdkalsdkfj {{ product.make }}</td>
            <td name="Model" class="cell">{{ product.model }}</td>
            <td name="Year" class="cell">{{ product.year }}</td>
            <td name="Color" class="cell">{{ product.color }}</td>
            <td name="Price" class="cell number">${{ product.price }}</td>
          </tr>
        </tbody>
      </table>
    </div>
    
  </section>
</template>

<style scoped lang="scss">
 section { margin: 1rem; }
 .table-overflow-container {
   overflow-x: auto;
   max-width: 100%;
 }
 table {
   table-layout: fixed;
   width: 100%;
   border-collapse: collapse;
 }
//  thead {
//    position: absolute;
//    margin: -9999rem;
//  }
 td { display: block; }
 td:before {
   content: attr(name) ':';
   margin-right: 1ch;
   color: lightslategrey;
   font-size: .875em;
 }
 tr {
   display: block;
   padding: 1rem;
   border: solid 1px #ddd;
 }
 tbody tr:nth-of-type(odd) {
   background: rgb(209, 237, 255);
 }

td[name="Make"] {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

 @media(min-width: 600px) {
   .l {
     width: 53%;
   }
   thead {
     position: relative;
     top: 0;
     left: 0;
   }
   tr { display: table-row; }
   td {
     display: table-cell;
     width: 500px;
     padding: 1ex 1ch;
   }
   td:before { content: none; }
 }

 
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
