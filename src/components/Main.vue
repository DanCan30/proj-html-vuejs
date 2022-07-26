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
    <section id="play-section">

      <div id="play-section-wrapper">
        <p>
          "I just listened to it and said to myself, "Man, I really love this album." Still, today, it just sounds so fresh.
          It sounds full of ideas. These guys knew what they were doing. They're good. And they're inventive. I haven't heard 
          anything this year that's as inventive. I don't really expect to."
        </p>
        <img src="../assets/img/band_interview_play_icon.png" alt="Play icon">
      </div>

    </section>

    <section id="live-date-section">
      <div id="live-date-wrapper">
        
      <h2>
        Live Dates
      </h2>
      <hr>
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rem, a! Corrupti sapiente voluptatem numquam.
      </p>
      <ul>
        <li><span>+</span>lorem</li>
        <li><span>+</span>lorem</li>
        <li><span>+</span>lorem</li>
        <li><span>+</span>lorem</li>
        <li><span>+</span>lorem</li>
      </ul>

      </div>
      <a href="#">view all live dates</a>

    </section>
    
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
    #article-section-wrapper p,
    #live-date-section p {
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

    #play-section {
      background-image: url(../assets/img/home-testimonial-parallax.jpg);
      background-size: cover;
      text-align: center;
      padding: 20rem 0;

      #play-section-wrapper {
        @include container;

        p {
        font-family: $mentionsFontFamily;
        color: $mainTextsFontColor;
        font-size: 2rem;
        }

        img {
          padding-top: 4rem;
          cursor: pointer;
        }
      }
    
    }
    
    #live-date-wrapper {
      @include large-container;
      padding-bottom: 8rem;

      ul {
        list-style: none;

        li {
          display: block;
          background-color: $lightBgColor;
          margin-bottom: 1rem;
          padding: .5rem 2rem;
          font-size: 1.3rem;
          letter-spacing: 3px;
          color: $brandMainColor;
          text-transform: uppercase;

          span {
            padding: 0 1rem;
            color: white;
            font-size: 1rem;
            cursor: pointer;
          }
        }
      }
    }
  
    
  }


</style>