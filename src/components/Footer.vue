<template>
  <footer>
    <section id="footer-top">
      <img src="../assets/img/logo_footer.png" alt="Avada Music logo">
      <ul class="footer-nav">
        <li v-for="(link, index) in navLinks" :key="index">
          <NavbarElement class="nav-links"
          :link="link"/>
        </li>
        
      </ul>
    </section>
    <section id="footer-bottom">
      <div id="copyrights">
        <span>© Copyright 2021 - 2020 | AVADA THEME BY THEMEFUSION | ALL RIGHTS RESERVED | POWERED BY ME</span>
      </div>
      <div id="socials">
        <ul>
          <li v-for="(social, index) in footerSocialIcons" :key="index"><a :href="social.url"><i :class="`fa-brands fa-${social.socialName}`"></i></a></li>
        </ul>
      </div>

    </section>
  </footer>
</template>

<script>
import NavbarElement from "./NavbarElement.vue";

export default {

  components: {
    NavbarElement,
  },

  props: {
    navLinks: {
      type: Array,
      required: true
    }
  },

  data: function() {
    return {
      
      footerSocialIcons: [
        {
          socialName: "facebook-f",
          url: "#",
        },
        {
          socialName: "twitter",
          url: "#",
        },
        {
          socialName: "instagram",
          url: "#",
        },
        {
          socialName: "youtube",
          url: "#",
        },
      ]
    }
  },

}
</script>

<style lang="scss">

@import "../assets/stiles/variables.scss";

  footer {
    background-color: $lightBgColor;

    #footer-top,
    #footer-bottom{
      padding: 5rem 4rem;
      display: flex;
      justify-content: space-between;
      align-items: center;

      ul {
        list-style: none;

      }

    }

    #footer-top {
      
        li {
          display: inline-block;
          font-family: $serifFont;
          padding: 0 .5rem;

          a.nav-links {
            text-decoration: none;
            padding: .5rem;
            transition: all .2s;
            color: #aeaeaeaf;
            font-size: 1.2rem;

            &:hover {
              color: $mainTextsFontColor;
            }
          }
        }
    }

    #footer-bottom {
      background-color: $darkBgColor;

      
      span {
        font-family: $serifFont;
        color: #aeaeaeaf;
      }

      #socials li{

        padding: 0 .5rem;
        display: inline-block;

        a {
          background-color: $lightBgColor;
          color: #aeaeaeaf;
          font-size: 1.2rem;              
          display: inline-block;
          border-radius: 5px;
          transition: all .2s;
          padding: 1rem 1.2rem;
          border-radius: 5px;
          transition: all .2s;

      
          &:hover {
            color: $mainTextsFontColor;
          }
        }

        &:first-child a {
          padding: 1rem 1.5rem;
        }
      }
    

    }
  }
</style>