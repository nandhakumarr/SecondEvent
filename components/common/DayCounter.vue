<template lang="pug">
.day-counter
  .countdown(v-if="timespan")
    .block
      .days
        p {{ timespan.days }}
        p.label Days
    .block
      .hours
        p {{ timespan.hours }}
        p.label Hours
    .block
      .minutes
        p {{ timespan.minutes }}
        p.label Minutes
    .block
      .seconds
        p {{ timespan.seconds }}
        p.label Seconds
</template>

<script>
import countdown from 'countdown'

export default {
  props: {
   eventDate: {
     type: Date,
     default: new Date()
   } 
  },
  data () {
    return {
      timespan: null
    }
  },
  methods: {
    countdown () {
      this.timespan =  countdown(
        this.eventDate, 
        null, 
        countdown.DAYS|countdown.HOURS|countdown.MINUTES|countdown.SECONDS
      )
    }
  },
  mounted () {
    setInterval(this.countdown, 1000)
  }
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'

$metric-size: 7rem

.day-counter
  .countdown
    @include flex
    justify-content: flex-start
    margin-bottom: $space*2
    @media (max-width: $breakpoint-minitab)
      margin-left: $space*-2.7
    @media (min-width: $breakpoint-mobile)
      margin-left: 0.2rem
      flex-wrap: wrap
    .block
      margin: $space
      text-align: center
      .days, .hours, .minutes, .seconds
        width: $metric-size
        height: $metric-size
      .days
        border: 3px solid $days
        border-radius: 50%
        padding: $space*2.2
        // @media (max-width: $breakpoint-minitab)
        //   border: none
        //   border-radius: 0
      .hours
        border: 3px solid $hours
        border-radius: 50%
        padding: $space*2
        // @media (max-width: $breakpoint-minitab)
        //   border: none
        //   border-radius: 0
      .minutes
        border: 3px solid $minutes
        border-radius: 50%
        padding: $space*2
        // @media (max-width: $breakpoint-minitab)
        //   border: none
        //   border-radius: 0
      .seconds
        border: 3px solid $seconds
        border-radius: 50%
        padding: $space*2
        // @media (max-width: $breakpoint-minitab)
        //   border: none
        //   border-radius: 0

p.label
  font-size: 10px
  text-transform: uppercase
  letter-spacing: 1px
p
  font-weight: 700
  font-size: 1.5rem

.days

</style>
