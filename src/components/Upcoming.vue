<template>
  <div class="element">

    <!-- Always visible thumbnail -->
    <div class="gig-thumbnail" @click="expandGigElement(gig)">
        <span class="expand-button" v-if="!gig.isSelected">+</span>
        <span class="collapse-button" v-else>-</span>
        <span class="gig">{{gig.date}} {{gig.eventName}} - {{(gig.country) ? gig.country + "," : ""}} {{gig.state}}</span>
    </div>
   
   <!-- Details are hidden by the overflow and becomes visible only when a thumbnail is clicked -->
    <div class="gig-info">
        <div class="gig-map">
            <img src="../assets/img/Map-placeholder.jpg" alt="Gig map">
        </div>
        <div class="gig-details">
            <h4>
                {{gig.eventName}}
            </h4>
            <p>
                {{gig.description}}
            </p>
            <a href="#">Book now</a>
        </div>
    </div>
    
  </div>
</template>

<script>
export default {
    props: {
        gig: {
            type: Object,
            required: true,
        }
    },
    
    methods: {
        expandGigElement: function(element) {
            (element.isSelected === false) ? element.isSelected = true : element.isSelected = false;
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/stiles/variables.scss";

    .gig-thumbnail {
        cursor: pointer;
    }

    .gig {
        font-size: 1.3rem;
        letter-spacing: 3px;
        color: $brandMainColor;
        text-transform: uppercase;
    }

    span.expand-button,
    span.collapse-button {
        display: inline-block;
        margin-right: 1.5rem;
        color: white;
    }

    span.collapse-button {
        background-color: $brandMainColor;
        margin-left: -.5rem;
        padding: 0 .5rem;
    }

    .gig-info {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 1.5rem;

        .gig-map {
            width: 25%;
            height: 15rem;
            overflow: hidden;

            img {
                width: 100%;
                height: 100%;
                object-fit: contain;
            }
        }

        .gig-details {
            width: 67%;

            h4 {
                color: white;
                text-transform: capitalize;
                font-size: 1.5rem;
                font-weight: 300;
                letter-spacing: 2px;
            }

            p {
                margin: 2rem 0;
                color: $paragraphsFontColor;
            }

            a {
                display: inline-block;
                text-transform: uppercase;
                padding: .75rem 2rem;
                text-decoration: none;
                color: white;
                background-color: $brandMainColor;
                transition: .2s;
                cursor: pointer;

                &:hover {
                    background-color: white;
                    color: $brandMainColor;
                    transform: scale(1.1);
                }
            }
        }
    }
    
</style>