<template>
  <div id="app" class="l-my-app">
    <Header class="l-header" />
    <Nav class="l-nav" />
    <Products class="l-products" />
    <aside class="l-aside">
      <Cart />
      <PaymentForm />
    </aside>
    <Footer class="l-footer" />
  </div>
</template>

<style lang="scss">
  @import url(./assets/scss/theme.scss);

@media (min-width: 600px) {
  .l-my-app {
    display: grid;
    grid-template-columns: 3fr 1fr;
    grid-template-areas: 
    "header header"
    "nav nav"
    "products aside"
    "footer footer"
    ;
  }
  .l-header { grid-area: header; }
  .l-nav { grid-area: nav; }
  .l-aside { grid-area: aside; }
  .l-footer { grid-area: footer; }
}

</style>

<script>
import Header from './components/header.vue'
import Nav from './components/nav.vue'
import Products from './components/products.vue'
import Cart from './components/cart.vue'
import PaymentForm from './components/payment-form.vue'
import Footer from './components/footer.vue'

export default {
  name: 'App',
  components: { Header, Nav, Products, Cart, PaymentForm, Footer }
}
</script>

