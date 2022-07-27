<template>
    <div class="card" :class="(article.isVertical) ? 'vertical-card' : 'horizontal-card'">

        <img :src="require(`../assets/img/${article.imageUrl}`)" :alt="article.title">

        <div class="article-infos">
          <h3>{{ article.title }}</h3>
          <p>{{article.subtitle}}</p>
        </div>

        <div class="hovered-div">
          <h3>{{ article.title }}</h3>
        </div>
    </div>
</template>

<script>
export default {

    props: {
        article: {
            type: Object,
            required: true,
        }
    }

}
</script>

<style lang="scss" scoped>
@import "../assets/stiles/variables.scss";

    .card {
        cursor: pointer;
        position: relative;
        overflow: hidden;
        
        img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: .1s;

        }

        .article-infos {
            padding: 2rem;
            background-color: $lightBgColor;
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            transition: .2s;



            h3 {
                font-size: 1.5rem;
                color: $brandMainColor;
            }

            p {
                color: $paragraphsFontColor;
                font-family: $serifFont;
                font-size: 1.3rem;
                line-height: 2rem;
            }
        }

        .hovered-div {
            display: flex;
            align-items: center;
            justify-content: center;
            position: absolute;
            top: 100%;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(234, 74, 86, .5);
            color: $mainTextsFontColor;
            transition: .2s;
            transition-delay: .1s;

            h3 {
                text-transform: capitalize;
                letter-spacing: 3px;
                font-weight: 300;
            }

        }

        &:hover {

        img {
            transform: scale(1.2);
        }

        .hovered-div {
            top: 0;

        } 
        
        .article-infos {
            bottom: -15rem;
        }
    }
    }


</style>