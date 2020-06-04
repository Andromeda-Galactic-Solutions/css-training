<template>
  <nav>
    <ul>
      <li><a href="">Home</a></li>
      <li><a href="">My Account</a></li>
      <li><a href="">Logout</a></li>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
  ul { padding-left: 0; }
  li { display: inline-block; }
  a { padding: 2ex 2ch; }
</style>

<script>
  export default { name: 'Nav' }
</script>
