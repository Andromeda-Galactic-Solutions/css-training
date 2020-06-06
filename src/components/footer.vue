<template>
  <footer>
    <a href="">Accessibility Statement</a>
  </footer>
</template>

<style scoped lang="scss">
  @use '../assets/scss/mixins.scss' as *; 
  footer {
    bottom: 0;
    border-top: solid 1px $border-color;
    padding: 1ex 1ch;
  }
</style>

<script>
  export default {
    name: 'Footer'
  }
</script>


