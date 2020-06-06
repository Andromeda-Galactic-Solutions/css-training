<template>
  <div class="app" id="app">
    <div class="top-bar">
      <Header />
      <Nav v-on:theme-change="toggleTheme()" />
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
  @use './assets/scss/mixins.scss' as *; 
  @import './assets/scss/theme.scss';
  .top-bar {
    padding: 1ex 2ch;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: white;
    border-bottom: solid 1px var(--primary);
    position: sticky;
    top: 0;
  }
  .table-container {
    width: 100%;
    overflow-x: auto;
  }
  .content {
    background: #fafafa;
    box-sizing: border-box;
    padding: 0 2ch;
    width: 100%;
  }
  @media (min-width: $small) {
    .content {
      display: flex;
      main { flex-grow: 1; }
      aside {
        width: 33%;
        flex-shrink: 0;
        flex-grow: 0;
        background: white;
        padding: 1rem;
        border-left: solid 1px $border-color;
      }
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
  components: { Header, Nav, Products, Cart, PaymentForm, Footer },
  methods: { toggleTheme }
}

function toggleTheme() {
  const app = document.getElementById('app')
  app.classList.toggle('alternate')
}
</script>

