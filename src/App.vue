<template>
  <div id="app">
    <Header 
    :navLinks="navLinks"/>
    <Main />
    <Footer  
    :navLinks="navLinks"/>
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
  },

  data: function() {
    return {
      navLinks: [
        {
          text: "Home",
          url: "#",
        },
        {
          text: "Meet The Band",
          url: "#",
        },
        {
          text: "Live Dates",
          url: "#",
        },
        {
          text: "Latest News",
          url: "#",
        },
        {
          text: "Albums",
          url: "#",
        },
        {
          text: "Fans",
          url: "#",
        },
      ],
      
    }
  }
}
</script>

<style lang="scss">

@import "./assets/stiles/common.scss";
@import "./assets/stiles/variables.scss";
@import "~@fortawesome/fontawesome-free/css/all.css";

</style>
