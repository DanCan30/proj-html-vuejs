<template>
  <div id="app">
    <Header />
    <Main />
    <Footer />
  </div>
</template>

<script>

import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer
  }
}
</script>

<style lang="scss">

@import "./assets/stiles/common.scss";
@import "./assets/stiles/variables.scss";
@import "~@fortawesome/fontawesome-free/css/all.css";

</style>
