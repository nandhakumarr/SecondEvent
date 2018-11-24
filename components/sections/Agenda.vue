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
          a(@click="select(i)",v-for="(day, i) in data", :key="i", :class="[ 'day' + i, { 'selected': selected === i }]")
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
    .cta
      a.btn more details
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
$day-size-tab: 15rem


section.agenda
  .container
    min-height: 100vh
    .head
      @include spread
      margin-bottom: $space*3.5
      @media (max-width: $breakpoint-tab-4)
        display: block
        margin-bottom: $space
      header
        flex: 1
        max-width: 50%
        text-align: left
        align-self: center
        @media (max-width: $breakpoint-tab-4)
          max-width: 100%
          margin-bottom: 3rem
        h2
          margin-bottom: $space*2
          margin-top: $space*2
          @media (max-width: $breakpoint-tab-4)
            margin-bottom: $space
          &:after
            content: ''
            @include absolute-w
        p
          margin-top: $space*5
          // padding: $space 0
          color: $neutral-light
          // width: $space*30

section.agenda
  .container
    .head
      .schedule-date
        flex: 1
        @media (max-width: $breakpoint-tab-portrait)
          height: 25rem
          position: relative
        .days
          position: relative
          min-height: 30rem
          margin: 0 auto
          @media (min-width: $breakpoint-tab-portrait) and (max-width: $breakpoint-tab-4)
            @include flex(center, center)
          @media (max-width: $breakpoint-tab-portrait)
            @include absolute
            width: 33rem
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
            cursor: pointer
            opacity: 0.5
            z-index: 1
            transition: all 0.4s ease
            @media (min-width: $breakpoint-tab-portrait) and (max-width: $breakpoint-tab-4)
              position: static
              margin: 0 1rem
            span.day
              font-size: 1.75rem
              text-transform: uppercase
              font-weight: 900
              line-height: 2rem
            span.date
              font-size: 1.5rem
            &.selected
              opacity: 1
              z-index: 3
              box-shadow: 0px 20px 30px 0px rgba(0, 0, 0, 0.12)
            &.day0
              background: linear-gradient(110deg, #fc6076 0%, #ff9a44 100%)
              top: $day-size*0.6
            &.day1
              background: linear-gradient(-45deg, #22e1ff 0%, #1d8fe1 49%, #625eb1 100%)
              left: $day-size*0.5
            &.day2
              background: -webkit-radial-gradient(50% 50%, circle closest-side, #57c6e1 0%, #b49fda 0%, #7ac5d8 0%, #eea2a2 0%, #b1aff0 0%, #836df0 100%)
              top: $day-size*0.4
              left: $day-size*1.2

section.agenda
  .container
    .sessions
      padding-bottom: $space*3
      .session
        @include spread
        flex-direction: row
        // height: 20rem
        // @media (max-width: $breakpoint-tab-4)
        //   height: 25rem
        // @media (max-width: $breakpoint-tab-portrait)
        //   border: 1px solid $neutral-light
        //   display: block
        //   margin-left: auto
        //   margin-right: auto
          // height: 20rem
          // width: 30rem
section.agenda
  .container
    .time
      margin-right: 2rem
      width: $space*11
      // height: 10rem
      position: relative
      padding: $space*3 $space*1.5
      background: $event-red
      flex: 0 0 20%
      max-width: 20%
      @media (max-width: $breakpoint-tab-portrait)
        width: 100%
        height: 7rem
        padding: 1.5rem
        margin: 0
        text-align: left

      h4
        color: $white
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
section.agenda
  .container
    .sessions
      .session-speaker
        margin-right: $space*6
        img
          width:  $space*5
          height:  $space*5
          border-radius: 50%
          @media (max-width: $breakpoint-tab-4)
            display: none
section.agenda
  .container
    .sessions
      .session-title
        .data
          @include flex-1
          @media (max-width: $breakpoint-tab-4)
            display: block
          h3


          span
            color: $neutral-light !important
        p
          padding-top: $space*2
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
  p
    padding: $space
    width: 63%
    color: $neutral-light !important
    @media (max-width: $breakpoint-tab-4)
      width: 100%
section.agenda
  .container
    width: 100%
    .cta
      width: 50%
      text-align: center
      margin-right: auto
      margin-left: auto
      padding-bottom: $space*4
</style>

