<template>
  <main>

    <section id="intro-section">
      <div id="intro-section-wrapper">
        <h2>
          Music is Life
        </h2>
        <hr>
        <p>
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rem, a! Corrupti sapiente voluptatem numquam.
        </p>
      </div>
    </section>

    <section id="article-section">
      <div id="article-section-wrapper">
        <h2>
          Latest Band News
        </h2>
        <hr>
        <p>
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rem, a! Corrupti sapiente voluptatem numquam.
        </p>
      </div>
    
      <div id="cards-container">
        <div class="card horizontal-card">
          <h3>lorem</h3>
          <p>1</p>
        </div>
        <div class="card vertical-card">
          <h3>lorem</h3>
          <p>2</p>
        </div>
        <div class="card vertical-card">
          <h3>lorem</h3>
          <p>3</p>
        </div>
        <div class="card vertical-card">
          <h3>lorem</h3>
          <p>4</p>
        </div>
        <div class="card vertical-card">
          <h3>lorem</h3>
          <p>5</p>
        </div>
        <div class="card horizontal-card">
          <h3>lorem</h3>
          <p>6</p>
        </div>
      </div>

    </section>
    <a href="#">view all latest news</a>
  </main>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>

@import "../assets/stiles/variables.scss";
@import "../assets/stiles/mixins.scss";

  main {
    background-color: $darkBgColor;

    section#intro-section {
      background-color: $lightBgColor;

    }
    
    div#intro-section-wrapper,
    div#article-section-wrapper {
      @include container;
    }

    div#cards-container {
      @include large-container;
    }

    h2 {
      color: $mainTextsFontColor;
      font-size: 4.5rem;
      padding: 5rem 0 2rem;
      text-align: center;
      letter-spacing: 2px;
    }

    hr {
      width: 20rem;
      margin: auto;
      color: $hrColor;
    }

    #intro-section-wrapper p,
    #article-section-wrapper p {
      font-family: Georgia, 'Times New Roman', Times, serif;
      max-width: 60rem;
      color: $paragraphsFontColor;
      margin: auto;
      padding: 3rem 0 5rem;
      text-align: center;
      line-height: 2.2rem;
      font-size: 1.3rem;
    }

    #cards-container {

      padding: 2rem 0 8rem;
      display: grid;
      gap: 2rem;
      grid-template-areas: 
      "first first second"
      "third fourth second"
      "third fourth fifth"
      "sixth sixth fifth" ;

      .card:first-child {
        grid-area: first;
      }
      .card:nth-child(2) {
        grid-area: second;
      }
      .card:nth-child(3) {
        grid-area: third;
      }
      .card:nth-child(4) {
        grid-area: fourth;
      }
      .card:nth-child(5) {
        grid-area: fifth;
      }
      .card:nth-child(6) {
        grid-area: sixth;
      }

      .card.vertical-card {
        background-color: salmon;
        height: 732px;
      }
      
      .card.horizontal-card {
        background-color: lightblue;
        height: 350px;

      }

    }

    a {
      display: block;
      text-transform: uppercase;
      text-align: center;
      background-color: $brandMainColor;
      color: $mainTextsFontColor;
      text-decoration: none;
      padding: 5rem;
      font-size: 1.5rem;
      letter-spacing: 3px;
    }

  }


</style>