<template>
  <div>
    <span>{{gig.date}} {{gig.eventName}} - {{(gig.country) ? gig.country +"," : ""}} {{gig.state}}</span>
  </div>
</template>

<script>
export default {
    props: {
        gig: {
            type: Object,
            required: true,
        }
    }
}
</script>

<style lang="scss" scoped>
    div {
        display: inline-block;
    }
</style>