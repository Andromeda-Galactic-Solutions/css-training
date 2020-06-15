<template>
  <div id="app">
    <Header />
    <Nav />
    <Products /> <!-- main -->
    <aside>
      <Cart />
      <PaymentForm />
    </aside>
    <Footer />
  </div>
</template>

<style lang="scss">
  @import url(./assets/scss/theme.scss);
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

