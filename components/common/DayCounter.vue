<template lang="pug">
.day-counter
  .countdown
    .block
      .days
        p 329
        p.label Days
    .block
      .hours
        p 02
        p.label Hours
    .block
      .minutes
        p 41
        p.label Minutes
    .block
      .seconds
        p 30
        p.label Seconds
</template>

<script>
// import moment from 'moment'
// import countdown from 'countdown'
// require('moment-countdown')

export default {
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
.day-counter
  .countdown
    @include flex
    justify-content: flex-start
    margin-bottom: $space*2
    @media (max-width: $breakpoint-minitab)
      margin-left: $space*-2.7
    .block
      margin: $space
      text-align: center
      .days
        border: 3px solid $days
        border-radius: 50%
        padding: $space*2.2
        @media (max-width: $breakpoint-minitab)
          border: none
          border-radius: 0
      .hours
        border: 3px solid $hours
        border-radius: 50%
        padding: $space*2
        @media (max-width: $breakpoint-minitab)
          border: none
          border-radius: 0
      .minutes
        border: 3px solid $minutes
        border-radius: 50%
        padding: $space*2
        @media (max-width: $breakpoint-minitab)
          border: none
          border-radius: 0
      .seconds
        border: 3px solid $seconds
        border-radius: 50%
        padding: $space*2
        @media (max-width: $breakpoint-minitab)
          border: none
          border-radius: 0

p.label
  font-size: 10px
  text-transform: uppercase
  letter-spacing: 1px
p
  font-weight: 700
  font-size: 1.5rem

.days

</style>
