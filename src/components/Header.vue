<template>
  <header id="top-page">

    <div id="topbar">
      <img src="../assets/img/avada-music-logo.png" alt="Avada Logo">
      <nav>
        <i class="fa-solid fa-bars"></i>
      </nav>
    </div>

    <section id="hero">
      <h1>Untold Stories</h1>
      <p>There is an untold story behind every favourite song.</p>
      <div id="button-container">
        <a href="#" class="main-btn">Latest album</a>
        <a href="#" class="secondary-btn">live dates</a>
      </div>
    </section>
    <a id="top-anchor" :class="{'visible': isScrolled}" href="#top-page"><i class="fa-solid fa-angle-up"></i></a>
  </header>

</template>

<script>

import Navbar from "./Navbar.vue";

export default {

  components: {
    Navbar
  },

  data: function() {
    return {
      isScrolled: false,
    }
  },

  props: {
    navLinks: {
      type: Array,
      required: true,
    }
  },

  methods: {
    scrollCheck: function() {
      if(window.scrollY !== 0) {
        this.isScrolled = true;
      } else {
        this.isScrolled= false;
      }
    }
  },


  created() {
    window.addEventListener("scroll", this.scrollCheck);
  }

}
</script>

<style lang="scss" scoped>
@import "../assets/stiles/variables.scss";

  header {

    background-image: url(../assets/img/home_slider.jpg);
    background-size: cover;

    #topbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 2rem 4rem;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;

      i {
        color: $mainTextsFontColor;
        font-size: 2rem;
        cursor: pointer;
      }

    }

    section#hero {
      padding-top: 25rem;
      text-align: center;

      h1 {
        font-size: 10rem;
        color: $mainTextsFontColor;
      }

      p {
        font-family: $mentionsFontFamily;
        font-size: 2rem;
        color: $mainTextsFontColor;
      }

      #button-container {
        display: inline-block;
        padding-bottom: 25rem;
        position: relative;

        &::after {
          display: inline-block;
          content: "";
          width: 100%;
          height: 1rem;
          background-color: $brandMainColor;
          position: absolute;
          bottom: -1rem;
          left: 0;
        }

        a {
          display: inline-block;
          text-transform: uppercase;
          text-decoration: none;
          padding: 1rem 2.5rem;
          letter-spacing: 4px;
          font-size: 1.2rem;
          border-radius: 3px;
          margin-top: 5rem;

          &.main-btn {
            color: $mainTextsFontColor;
            background-color: $brandMainColor;
            margin-right: 1rem;
          }

          &.secondary-btn {
            color: $mainTextsFontColor;
            border: 1px solid $mainTextsFontColor;
            margin-left: 1rem;
          }
        }
      }

    
    }

    #top-anchor {
      display: inline-block;
      padding: .5rem 1.5rem;
      border-radius: 10px 10px 0 0;
      background-color: #323233;
      position: fixed;
      bottom: -3rem;
      right: 5rem;
      font-size: 1rem;
      color: $mainTextsFontColor;
      transition: 1s;

      &.visible {
        bottom: 0;
      }
    }
  }
  
  
  

</style>