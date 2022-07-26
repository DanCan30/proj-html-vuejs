<template>
  <footer>
    <section id="footer-top">
      <img src="../assets/img/logo_footer.png" alt="Avada Music logo">
      <ul>
        <li v-for="(link, index) in footerNavLinks" :key="index"><a :href="link.url"> {{ link.text }} </a></li>
        
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
export default {
  data: function() {
    return {
      footerNavLinks: [
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
  }
}
</script>

<style lang="scss" scoped>

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

        li {
          display: inline-block;
          font-family: $serifFont;
          padding: 0 .5rem;

          a {
            text-decoration: none;
            color: #aeaeaeaf;
            font-size: 1.2rem;              
            display: inline-block;
            background-color: $lightBgColor;
            padding: 1rem;
            border-radius: 5px;

            &:hover {
              color: $mainTextsFontColor;
            }
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

      #socials li:first-child a {
        padding: 1rem 1.2rem;
      }

    }
  }
</style>