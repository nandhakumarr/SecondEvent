<template lang="pug">
section.hero
  .container
    .banner-content
      p 5 to 7 June 2019, Waterfront Hotel, London
      h1 Digital Thinkers MeetUp
      .timer
      day-counter(:event-date="eventDate")
      .cta
        a.btn Buy Ticket
    .banner-img
      img(src="/images/banner-img.png", height="720")
</template>

<script>
import DayCounter from '~/components/common/DayCounter'
export default {
  data () {
    return {
      eventDate: new Date('2019-Jan-04 18:30:00')
    }
  },
  components: {
    DayCounter
  }
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.hero
  background-image: url(/images/banner-bg.jpg)
  background-repeat: no-repeat
  background-size: cover
  color: $white
  padding-top: $space*9
  height: 800px
  overflow: hidden
  .container
    @include flex
    .banner-content
      margin-bottom: $space*15
      @media (max-width: $breakpoint-mobile)
        margin-bottom: $space*5
        width: 20rem
      h1
        text-transform: uppercase
        margin-bottom: $space*3.5
        margin-top: $space*2
        line-height: 1.2
        @media (max-width: $breakpoint-tab-1)
          font-size: 2rem
        @media (max-width: $breakpoint-mobile)
          font-size: 1.8rem
    .banner-img
      // position: relative
      img
        max-width: 100%
        vertical-align: middle
      @media (max-width: $breakpoint-tab-1)
        display: none
// section.hero
//   .container
//     .banner-content
//       .timer
//         @media (max-width: $breakpoint-mobile)
//           width: 25rem

</style>

