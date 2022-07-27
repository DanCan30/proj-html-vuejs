<template>
  <header id="top-page">

    <div id="topbar">
      <img src="../assets/img/avada-music-logo.png" alt="Avada Logo">

        <!-- Hidden navbar -->
      <nav>     

        <i @click="expandNavbar()" class="fa-solid fa-bars"></i>
          
        <div id="header-navbar" :class="{'expanded': navExpanded === true}">
          <i v-show="navExpanded" @click="collapseNavbar()" class="fa-solid fa-xmark"></i>
          <ul>
            <li v-for="(link, index) in navLinks" :key="index">
              <NavbarElement
              :link="link"
               @click.native="collapseNavbar()"/>
            </li>
          </ul>
        </div>

      </nav>
    </div>

    <section id="hero">
      <h1>Untold Stories</h1>
      <p>There is an untold story behind every favourite song.</p>
      <div id="button-container">
        <a href="#" class="main-btn">Latest album</a>
        <a href="#live-date-section" class="secondary-btn">live dates</a>
      </div>
    </section>

    <!-- Anchor to top -->
    <a id="to-top-anchor" :class="{'visible': isScrolled}" href="#top-page"><i class="fa-solid fa-angle-up"></i></a>
  </header>

</template>

<script>

import NavbarElement from "./NavbarElement.vue";

export default {

  components: {
    NavbarElement
  },

  props: {
    navLinks: {
      type: Array,
      required: true
    }
  },

  data: function() {
    return {
      isScrolled: false,

      navExpanded: false,
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
    },

    expandNavbar: function() {
      this.navExpanded = true;
    },

    collapseNavbar: function() {
      this.navExpanded = false;
    }
  },


  created() {
    window.addEventListener("scroll", this.scrollCheck);
  }

}
</script>

<style lang="scss">
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
      z-index: 1;
      top: 0;
      left: 0;
      width: 100%;

      img {
        z-index: 2;
      }

      #header-navbar {
        background-color: $brandMainColor;
        position: absolute;
        top: 0;
        right: 0;
        left: 100%;
        transition: all .3s;

        &.expanded {
          left: 0;
        }

        i {
          color: $mainTextsFontColor;
          font-size: 2.5rem;
          cursor: pointer;
          position: absolute;
          top: 3rem;
          right: 4rem;
        }

        ul {
          list-style: none;
          padding: 8rem 0 5rem;

          li {
            text-align: center;
            padding: 1rem;

            a {
              color: $mainTextsFontColor;
              text-decoration: none;
              font-size: 2.5rem;
              opacity: .5;
              position: relative;
              font-weight: 300;

              &::after {
                content: "";
                display: inline-block;
                background-color: white;
                height: 2px;
                width: 0;
                position: absolute;
                bottom: 0;
                left: 0;
                transition: .3s;
              }

              &:hover {
                opacity: 1;
              }

              &:hover::after {
                width: 100%;
              }


            }
          }
        }
      }

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
        width: 34rem;


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
          letter-spacing: 3px;
          font-size: 1.2rem;
          border-radius: 3px;
          margin-top: 5rem;
          transition: .3s;

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

          
          &:hover {
            background-color: white;
            color: black;
            letter-spacing: 5px;
          }

        }
      }
    }

    #to-top-anchor {
      display: inline-block;
      padding: .5rem 1.5rem;
      border-radius: 10px 10px 0 0;
      background-color: #323233;
      position: fixed;
      bottom: -3rem;
      right: 5rem;
      font-size: 1rem;
      color: $mainTextsFontColor;
      transition: .2s;

      &:hover {
        background-color: $brandMainColor;
        transform: scale(1.4);
      }

      &.visible {
        bottom: 0;
      }
    }
  }
  
  
  

</style>