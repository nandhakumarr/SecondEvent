<template lang="pug">
section.hero
  .container
    app-header

</template>

<script>
import AppHeader from '~/components/sections/AppHeader.vue'
export default {
  components: {
    AppHeader
  }

}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.hero
  background-image: url(/images/banner-bg.jpg)
  background-repeat: no-repeat
  background-size: cover
  background-position: center center
  min-height: 100vh
</style>

