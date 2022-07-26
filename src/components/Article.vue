<template>
    <div class="card" :class="(article.isVertical) ? 'vertical-card' : 'horizontal-card'">

        <img :src="require(`../assets/img/${article.imageUrl}`)" :alt="article.title">

        <div class="article-infos">
          <h3>{{ article.title }}</h3>
          <p>{{article.subtitle}}</p>
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
        
        img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        }

        .article-infos {
            padding: 2rem;
            background-color: $lightBgColor;
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;

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
    }

</style>