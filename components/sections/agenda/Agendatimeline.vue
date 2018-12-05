<template lang="pug">
section.agenda
  .container
    header
      span SCHEDULE DETAILS
      h2 Event Schedules
      .schedule-date
        nav.days
          a(@click="select(i)",v-for="(day, i) in data", :key="i", :class="{'btn-primary': selected === i }")
            h3.date {{ day.date }}
            h6.day {{ day.day }}
    main
      .sessions(v-if="selected === i", v-for="(day, i) in data", :key="i")
        .session(v-for="(s, j) in day.session", :key="j")
          .speaker-image(v-if="s.image")
            img(v-if="s.image", :src="s.image")
          .description
            h4.time {{ s.start_time }} - {{ s.end_time }}
            h3.title {{ s.title }}
            span.tag {{ s.tag_name }}
            p.content {{ s.content }}
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

$br-split: $page-width
section.agenda
  background: #FFF
  .container
    header
      text-align: center

section.agenda
  background: #FFF
  .container
    .schedule-date
      text-align: center
      nav.days
        @include flex
        justify-content: center
        position: relative
        a
          margin: $space
          background: #f1f0f6
          padding: $space $space*3.2
          cursor: pointer
          position: relative
          &.btn-primary
            background: $event-color
            h6, h3
              color: $white !important
            &:before
              border-style: solid
              border-width: 0 15px 15px 0
              border-color: transparent #e7015e transparent transparent
              position: absolute
              left: 0
              bottom: -15px
              content: ''
              opacity: 1
              transition: all 0.4s ease
          h3, h6
            color: #000 !important
            font-weight: normal
            margin: $space/2
          h6
            text-transform: uppercase


//photo
.session
  .speaker-image
    img
      border-radius: 50%
      width: 5rem
      box-shadow: 19.799px 19.799px 40px 0px rgba(0, 0, 0, 0.1)

//description
.session
  .description
    h4.time
      color: $event-color !important
      font-size: 14px
      font-weight: normal
    h3.title
      font-weight: bold
    .tag, .content
      color: $neutral

//layout
.sessions
  // max-width: $br-split/2
  .session
    @include flex
    align-items: flex-start
    border-right: 1px solid $neutral
    &:nth-child(even)
      flex-direction: row-reverse
      text-align: right
      img
        box-shadow: -19.799px 19.799px 40px 0px rgba(0, 0, 0, 0.1)
    .description
      flex: 1
      padding: $space/2 $space
      // max-width: 30rem

//responsive

.session
  @media (max-width: $br-split)
    max-width: $br-split/2
</style>

