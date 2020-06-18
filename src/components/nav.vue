<template>
  <nav>
    <ul>
      <li><a href="./index.html">Home</a></li>
      <li><a href="">My Account</a></li>
      <li><a href="">Logout</a></li>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
nav {
  text-align: right;
}
ul {
  padding-left: 0;
  margin: 0;
}
li { display: inline-block; margin: 1ch; }
a { padding: 2ex 1ch; }
</style>

<script>
export default { name: "Nav" };
</script>
