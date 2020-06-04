<template>
  <div id="app">
    <Header />
    <br>
    <Nav />
    <br>
    <Products />
    <br>
    <Cart />
    <br>
    <PaymentForm />
    <br>
    <Footer />
  </div>
</template>

<style scoped lang="scss"></style>

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

