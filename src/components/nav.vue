<template>
  <nav>
    <ul>
      <li>
        <a href="">Home</a>
      </li>
      <li>
        <a href="">My Account</a></li>
      <li><a href="">Logout</a></li>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
// ITCSS Component & Layout
nav {
  width: 100%;
  text-align: right;
}
nav li {
  display: inline-block;
  margin: 0.2rem 1rem;
}
// ITCSS Component & Skin/Theme
nav {
  background: #edecec;
}
</style>

<script>
  export default { name: 'Nav' }
</script>
