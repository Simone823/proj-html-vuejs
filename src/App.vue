<template>

  <!-- App vue -->
  <div id="app">
    <MyHeader/>
    <NavMenu/>

    <main>
      <Section_1/>
      <Section_2/>
      <Section_3/>
      <Section_4/>
      <Section_5/>
      <Section_6/>
      <Section_7/>
    </main>

    <Footer/>
    <FooterBanner/>

  </div>

</template>



<script>
// Import MyHeader
import MyHeader from "./components/MyHeader.vue";

// Import NavMenu
import NavMenu from "./components/NavMenu.vue";

// Import Section_1
import Section_1 from "./components/Section_1.vue";

// Import Section_2
import Section_2 from "./components/Section_2.vue";

// Import Section_3
import Section_3 from "./components/Section_3.vue";

// Import Section_4
import Section_4 from "./components/Section_4.vue";

// Import Section_5
import Section_5 from "./components/Section_5.vue";

// Import Section_6
import Section_6 from "./components/Section_6.vue";

// Import Section_7
import Section_7 from "./components/Section_7.vue";

// Import Section_8
import Footer from "./components/Footer.vue";

// Import FooterBanner
import FooterBanner from "./components/FooterBanner.vue";


export default {
  name: 'App',
  components: {
    MyHeader,
    NavMenu,
    Section_1,
    Section_2,
    Section_3,
    Section_4,
    Section_5,
    Section_6,
    Section_7,
    Footer,
    FooterBanner,
  },
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
