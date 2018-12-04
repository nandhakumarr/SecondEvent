<template lang="pug">
section.agenda
  .container
    .head
      header
        span SCHEDULE DETAILS
        h2 Event Schedules
      .schedule-date
        nav.days
          a(@click="select(i)",v-for="(day, i) in data", :key="i", :class="[ 'day' + i, { 'selected': selected === i }]")
            span.day {{ day.day }}
            span.date {{ day.date }}

    main
      .sessions(v-if="selected === i", v-for="(day, i) in data", :key="i")
        .session(v-for="(s, j) in day.session", :key="j")
          .details
            .session-speaker
              img(v-if="s.image", :src="s.image")
            .session-title
              .time
                h4 {{ s.start_time }} - {{ s.end_time }}
                //- h6 {{ s.event }}
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

section.agenda
  background: #FFF
  .container
    .head
      header
        text-align: center

section.agenda
  background: #FFF
  .container
    .head
      .schedule-date
        text-align: center
        nav.days
          a 
          span , span
            color: black


section.agenda 
  .container
    main
      .sessions
        .details
          @include flex-1
          .session-speaker
            img
              margin-left: 1rem
              width: 5rem 
              border-radius: 50%
          .session-title
            padding: 2rem
            .time
              margin-bottom: 0.75rem
              h4, h6
                color: $event-red
                font-size: 0.75rem
            .data 
              margin-bottom: 1rem
              h3, span
                color: black
            p 
              color: black
              width: 35%

h4.lunch, h3.lunch, span.lunch
  display: none

.details
  &:nth-child(even)
    
</style>

