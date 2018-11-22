<template lang="pug">
section.agenda
  .container
    .head
      header
        span SCHEDULE DETAILS
        h2 Information of Event Schedules
        p World is committed to making participation in the event a harassment free experience for everyone, regardless of level of experience, gender, gender identity and expression
      nav.days
        a(@click="select(i)",v-for="(day, i) in data", :key="i", :class="day.day")
          span.day {{ day.day }}
          span.date {{ day.date }}

    main   
      .sessions(v-if="selected === i", v-for="(day, i) in data", :key="i")
        .session(v-for="(s, j) in day.session", :key="j")
          .time
            h4 {{ s.start_time }} - {{ s.end_time }}
            h6 {{ s.event }}
          .details
            .session-speaker
              img(:src="s.image")
            .session-title
              .data
                h3 {{ s.title }}
                span {{ s.tag_name }}
              p {{ s.content }}
</template>

<script>
import session from 'static/seed/session'
export default {
  data () {
    return {
      data: session,
      selected: 0
    }
  },
  methods: {
    select (i) {
      this.selected = i
    }
  }

}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'

$day-size: 15rem


section.agenda
  .container
    min-height: 100vh
    .head
      @include flex-1
      margin-bottom: $space*5
      @media (max-width: $breakpoint-tab-4)
        display: block
      header
        padding: $space
        span
          padding: $space 0
          color: $neutral-light
        h2
          margin-top: $space*1.5
          margin-bottom: $space*3.5
        p
          padding: $space 0
          color: $neutral-light
          width: $space*30
      .days
        position: relative
        height: 20rem
        width: 20rem
        margin: 0 auto
        @media (max-width: $breakpoint-tab-4)
          @include flex
        a
          @include flex-1
          padding:  $space
          background: linear-gradient(110deg, #fc6076 0%, #ff9a44 100%)
          border-radius: 50%
          color: $neutral-light
          width: $day-size
          height: $day-size
          align-items: center
          justify-content: center
          color: $white
          flex-direction: column
          position: absolute
        
          @media (max-width: $breakpoint-tab-4)
            position: static
          &.friday
            background: linear-gradient(110deg, #fc6076 0%, #ff9a44 100%)
            z-index: 3
            top: $day-size*0.5
          &.saturday
            background: linear-gradient(-45deg, #22e1ff 0%, #1d8fe1 49%, #625eb1 100%)
            opacity: 0.5
            z-index: 2
            left: $day-size*0.5
          &.sunday
            background: radial-gradient(50% 50%, circle closest-side, #57c6e1 0%, #b49fda 0%, #7ac5d8 0%, #eea2a2 0%, #b1aff0 0%, #836df0 100%)
            opacity: 0.5
            z-index: 1
            top: $day-size*0.65
            left: $day-size*0.75
          span.day
            font-size: 1.75rem
            text-transform: uppercase
            font-weight: 900
            line-height: 2rem
          span.date
            font-size: 1.5rem

section.agenda
  .container
    .session
      @include spread
      // border: 1px dotted $neutral-light
      .time 
        margin-right: 2rem
        width: $space*11
        background: $event-red
        height: 10rem
        text-align: center
        h4
          color: $neutral-light
          margin-top: $space*3
        h6
          font-size: $space*1.25
          color: $neutral-light
      .details
        height: $space*10
        flex: 1
        width:  $space*10
        @include flex
        .session-speaker
          margin-right:  $space*3
          img
            width:  $space*5
            height:  $space*5
            border-radius: 50%
        .session-title
          .data
            @include flex-1
            h3
              padding: $space
              color: $neutral-light
            span
              padding: $space
              color: $neutral-light !important
          p
            padding: $space
            width: 63%
            color: $neutral-light !important
      
</style>

