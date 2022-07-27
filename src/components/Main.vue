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

      <div id="article-title-wrapper">
        <h2>
          Latest Band News
        </h2>
        <hr>
        <p>
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rem, a! Corrupti sapiente voluptatem numquam.
        </p>
      </div>
    
      <div id="cards-container">

        <Article v-for="(article, index) in articles" :key="index"
        :article="article" 
        />

      </div>

    </section>

    <a href="#article-section">view all latest news</a>
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
          <li v-for="(gig, index) in upcomingGigs" :key="index"  :class="{'expanded': gig.isSelected}">
            <Upcoming 
            :gig="gig"/>
          </li>
        </ul>

      </div>
      <a href="#">view all live dates</a>

    </section>
    
  </main>
</template>

<script>

import Article from "./Article.vue";
import Upcoming from "./Upcoming.vue";


export default {

  components: {
    Article,
    Upcoming,
  },


  data: function() {
    return {
      articles: [
        {
          title: "Technology and music",
          subtitle: " Lorem ipsum dolor, sit amet consectetur adipisicing elit.",
          imageUrl: "blog_music_techo.jpg",
          isVertical: false,
        },
        {
          title: "Taking it back to the old school",
          subtitle: " Lorem ipsum dolor, sit amet consectetur adipisicing elit.",
          imageUrl: "blog-post1.jpg",
          isVertical: true,
        },
        {
          title: "While my guitar gently weeps",
          subtitle: " Lorem ipsum dolor, sit amet consectetur adipisicing elit.",
          imageUrl: "blog-post3.jpg",
          isVertical: true,
        },
        {
          title: "It just sounds better",
          subtitle: " Lorem ipsum dolor, sit amet consectetur adipisicing elit.",
          imageUrl: "blog-post4.jpg",
          isVertical: true,
        },
        {
          title: "Sharing the stage with a legend",
          subtitle: " Lorem ipsum dolor, sit amet consectetur adipisicing elit.",
          imageUrl: "blog-post2.jpg",
          isVertical: true,
        },
        {
          title: "The flavor of rock",
          subtitle: " Lorem ipsum dolor, sit amet consectetur adipisicing elit.",
          imageUrl: "blog_flavor_rock.jpg",
          isVertical: false,
        },
      ],

      upcomingGigs: [
        {
          date: "17/08/2020",
          eventName: "gem festival 2020",
          country: "anakalia",
          state: "georgia",
          description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum quo totam maxime consectetur magnam amet ipsum atque quia non debitis repudiandae, provident excepturi iste. Voluptate voluptatum cupiditate dolor autem veniam.",
          isSelected: false,
        },
        {
          date: "24/09/2020",
          eventName: "groovefest",
          state: "dominical republic",
          description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum quo totam maxime consectetur magnam amet ipsum atque quia non debitis repudiandae, provident excepturi iste. Voluptate voluptatum cupiditate dolor autem veniam.",
          isSelected: false,
        },
        {
          date: "31/10/2020",
          eventName: "oasis festival 2020",
          country: "marrakech",
          state: "morocco",
          description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum quo totam maxime consectetur magnam amet ipsum atque quia non debitis repudiandae, provident excepturi iste. Voluptate voluptatum cupiditate dolor autem veniam.",
          isSelected: false,
        },
        {
          date: "07/11/2020",
          eventName: "moga festival",
          country: "essaouria",
          state: "morocco",
          description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum quo totam maxime consectetur magnam amet ipsum atque quia non debitis repudiandae, provident excepturi iste. Voluptate voluptatum cupiditate dolor autem veniam.",
          isSelected: false,
        },
        {
          date: "10/12/2020",
          eventName: "envision festival",
          country: "uvita",
          state: "costa rica",
          description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum quo totam maxime consectetur magnam amet ipsum atque quia non debitis repudiandae, provident excepturi iste. Voluptate voluptatum cupiditate dolor autem veniam.",
          isSelected: false,
        },
      ]
    }
  },

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
    #article-title-wrapper p,
    #live-date-section p {
      font-family: $serifFont;
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
        height: 732px;
      }
      
      .card.horizontal-card {
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
      transition: .3s;

      &:hover {
        background-color: white;
        color: black;
        letter-spacing: 5px;
      }
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
          transition: .2s;

          &:hover {
            transform: scale(1.1);
          }
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
          padding: .8rem 2rem;
          height: 60px;
          overflow: hidden;

          &.expanded {
            height: 100%;
          }

          span {
            padding: 0 1rem;
            color: white;
            font-size: 1rem;
          }
        }
      }
    }
  }


</style>