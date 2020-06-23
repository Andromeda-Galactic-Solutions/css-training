<template>
  <div id="app">
    <div class="top-bar">
      <Header />
      <Nav />
    </div>
    <div class="content">
      <Products />
      <aside>
        <Cart />
        <PaymentForm />
      </aside>
    </div>
    <Footer />
  </div>
</template>

<style lang="scss">
  @use './assets/scss/theme.scss';
</style>

<style scoped lang="scss">
.top-bar {
  padding: 1ex 2ch;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: sticky;
  top: 0;
}
.content {
  background: #fafafa;
  box-sizing: border-box;
  padding: 0 2ch;
  width: 100%;
}

@media(min-width: 600px) {
  .content {
    display: flex;
  }
  .content main {
    flex-grow: 1;
  }
  .content aside {
    width: 33%;
    flex-shrink: 0;
    flex-grow: 0;
    background: #ffffff;
  }
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

