<template>

    <a :href="link.url"> {{ link.text }} </a>

</template>

<script>
export default {
    
  props: {
    link: {
      type: Object,
      required: true,
    }
  },

}
</script>

<style>

</style>