<template>
  <footer>
    <section id="footer-top">
      <img src="../assets/img/logo_footer.png" alt="Avada Music logo">
      <ul>
        <li><a href="#"> lorem </a></li>
        <li><a href="#"> lorem </a></li>
        <li><a href="#"> lorem </a></li>
        <li><a href="#"> lorem </a></li>
        <li><a href="#"> lorem </a></li>
        <li><a href="#"> lorem </a></li>
      </ul>
    </section>
    <section id="footer-bottom">
      <div id="copyrights">
        <span>© Copyright 2021 - 2020 | AVADA THEME BY THEMEFUSION | ALL RIGHTS RESERVED | POWERED BY ME</span>
      </div>
      <div id="socials">
        <ul>
          <li><a href="#">social</a></li>
          <li><a href="#">social</a></li>
          <li><a href="#">social</a></li>
          <li><a href="#">social</a></li>
        </ul>
      </div>

    </section>
  </footer>
</template>

<script>
export default {

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
          padding: 0 1rem;

          a {
            text-decoration: none;
            color: #aeaeaeaf;
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
    }
  }
</style>