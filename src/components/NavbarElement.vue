<template>

  <div>
    <a :href="link.url"> {{ link.text }} </a>
  </div>

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