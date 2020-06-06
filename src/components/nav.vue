<template>
  <nav>
    <ul>
      <li><a href="">Home</a></li>
      <li><a href="">My Account</a></li>
      <li><a href="">Logout</a></li>
      <li>
        <button type="button" v-on:click="toggleTheme()">
          Toggle Theme
        </button>
      </li>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
  nav { text-align: right; }
  ul {
    padding-left: 0;
    margin: 0;
  }
  li { display: inline-block; }
  a { padding: 2ex 2ch; }
</style>

<script>
  export default {
    name: 'Nav',
    data: () => ({reactive: true}),
    methods: { toggleTheme }
  }
  let alternateTheme = false
  function toggleTheme() {
    alternateTheme = !alternateTheme
    this.$emit('theme-change', alternateTheme)
  }

</script>
