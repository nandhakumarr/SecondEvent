<template lang="pug">
section.agenda
  .container
    .head
      header
        span SCHEDULE DETAILS
        h2 Information of Event Schedules
        p World is committed to making participation in the event a harassment free experience for everyone, regardless of level of experience, gender, gender identity and expression
      .schedule-date
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
              img(v-if="s.image", :src="s.image")
            .session-title
              .data
                h3(:class="s.class") {{ s.title }}
                span(:class="s.class") {{ s.tag_name }}
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
      @include spread
      margin-bottom: $space*5
      // @media (max-width: $breakpoint-tab-4)
      //   display: block
      header
        flex: 1
        max-width: 50%
        text-align: left
        align-self: center
        h2
          margin-bottom: $space*2
          margin-top: $space*2
          &:after
            content: ''
            @include absolute-w
        p
          margin-top: $space*5
          // padding: $space 0
          color: $neutral-light
          // width: $space*30
      .schedule-date
        flex: 1
        max-width: 50%
        align-self: center
        .days
          position: relative
          min-height: 30rem
          margin: 0 auto
          @media (max-width: $breakpoint-tab-4)
            width: 100%
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
            @media (max-width: $breakpoint-tab-portrait)
              position: absolute
              width: $day-size/1.5
              height: $day-size/1.5

            &.friday
              background: linear-gradient(110deg, #fc6076 0%, #ff9a44 100%)
              z-index: 3
              top: $day-size*0.7
            &.saturday
              background: linear-gradient(-45deg, #22e1ff 0%, #1d8fe1 49%, #625eb1 100%)
              opacity: 0.5
              z-index: 2
              left: $day-size*0.5
            &.sunday
              background: -webkit-radial-gradient(50% 50%, circle closest-side, #57c6e1 0%, #b49fda 0%, #7ac5d8 0%, #eea2a2 0%, #b1aff0 0%, #836df0 100%)
              opacity: 0.5
              z-index: 1
              @include absolute-ne
              top: 6rem
              left: 15rem
            span.day
              font-size: 1.75rem
              text-transform: uppercase
              font-weight: 900
              line-height: 2rem
            span.date
              font-size: 1.5rem

section.agenda
  .container
    .sessions
      padding-bottom: $space*3
      .session
        @include spread
        flex-direction: row
        // border: 1px dotted $neutral-light
        // height: 10rem
        @media (max-width: $breakpoint-tab-4)
          border: 1px solid $neutral-light
          display: block
          margin-left: auto
          margin-right: auto
          height: 20rem
          width: 30rem


        .time
          // margin-right: 2rem
          // width: $space*11
          height: 10rem
          position: relative
          padding: $space*3 $space*1.5
          background: $event-red
          // text-align: center
          flex: 0 0 20%
          max-width: 20%
          @media (max-width: $breakpoint-tab-4)
            width: 100%
            height: 7rem
            padding: 1.5rem
            margin: 0
            text-align: left

          h4
            color: $white
            // margin-top: $space*3
            @media (max-width: $breakpoint-tab-4)
              margin-top: 0
          h6
            font-size: 1.25rem
            color: $white
        .details
          flex: 100%
          height: 10rem
          position: relative
          padding: 35px 40px 35px 60px
          border: 1px dashed #e5e5e5
          border-left: none
          width: 100%
          @include flex
          @media (max-width: $breakpoint-tab-4)
            display: block
            width: 100%
          .session-speaker
            margin-right: $space*6
            img
              width:  $space*5
              height:  $space*5
              border-radius: 50%
              // margin-right: $space*4
          //     @media (max-width: $breakpoint-tab-4)
          //       display: none
          .session-title
            .data
              @include flex-1
              @media (max-width: $breakpoint-tab-4)
                display: block
              h3

              span
                // padding: $space
                color: $neutral-light !important
                // margin-left: $space*10
            p
              padding-top: $space*2
              // width: 63%
              color: $neutral-light !important
              @media (max-width: $breakpoint-tab-4)
                width: 100%

.session
  &:nth-child(even)
    .time
      background: $event-color !important

h3.lunch,
span.lunch
  @include absolute-nw
  left: 15rem
  margin-top: $space*3

span.lunch
  margin-left: $space*10
</style>

