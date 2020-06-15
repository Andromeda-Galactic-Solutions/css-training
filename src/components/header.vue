<template>
  <header class="header">
    <img class="header__logo" src="../assets/img/logo.png" alt="CSS three logo in dark blue">
    <div class="header__title">CSS Training</div>
  </header>
</template>

<style scoped lang="scss">
.header {
  padding: 1rem;
}
.header__logo {
  width: 64px;
}
.header__title {
  display: inline-block;
}
// Theme
.header__title {
  font-size: 2.5rem;
  font-weight: bold;
}
</style>

<script>
export default {
  name: 'Header',
}
</script>
