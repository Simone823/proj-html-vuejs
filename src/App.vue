<template>

  <!-- App vue -->
  <div id="app">
    <MyHeader/>
    <NavMenu/>

    <main>
      <Section_1/>
    </main>

  </div>

</template>



<script>
// Import MyHeader
import MyHeader from "./components/MyHeader.vue";

// Import NavMenu
import NavMenu from "./components/NavMenu.vue";

// Import Section_1
import Section_1 from "./components/Section_1.vue";

export default {
  name: 'App',
  components: {
    MyHeader,
    NavMenu,
    Section_1,
  }
}
</script>



<style lang="scss">
// Import common scss
@import '../src/assets/scss/common.scss';

#app {
  font-family: "Quicksand", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
