<template>

  <!-- App vue -->
  <div id="app">
    <MyHeader/>
  </div>

</template>

<script>
// Import MyHeader
import MyHeader from "./components/MyHeader.vue"

export default {
  name: 'App',
  components: {
    MyHeader,
  }
}
</script>

<style lang="scss">
// Import common scss
@import '../src/assets/scss/common.scss';

#app {
  font-family: "Nunito", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
