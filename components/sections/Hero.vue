<template lang="pug">
section.hero
  .container
    app-header
    .banner-content
      p 5 to 7 June 2019, Waterfront Hotel, London
      h1 Digital Thinkers MeetUp
      .timer
      .cta
        a.btn Buy Ticket
    .banner-img
      img(src="/images/banner-img.png")
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
  // min-height: 75vh
  color: $white
  padding-top: $space*12
  .container
    @include spread
    .banner-content
      h1
        text-transform: uppercase
        margin-bottom: $space*3.5
        margin-top: $space*2
        line-height: 1.2
        @media (max-width: $breakpoint-tab-1)
          font-size: 1.8rem
    .banner-img
      position: relative
      min-height: 1px
      img
        vertical-align: middle
      //   @include absolute-e
      @media (max-width: $breakpoint-tab-1)
        display: none
</style>

