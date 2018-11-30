<template lang="pug">
section.venue
  .container
    header
      span REACH US
      h2 Get Direction to Event Hall
    main
      .location-details
        nav
          a.btn(@click="select(i)", v-for="(v, i) in data", :key="i", :class="{'btn-primary': selected === i }")  {{ v.tab_name }}
        .content
          .detail(v-if="selected === i", v-for="(v,i) in data", :key="i")
            .details(v-for="(s,j) in v.venuetabs" :key="j")
              h3 {{ s.heading }}
              p {{ s.address }}
              .contact
                .ticketinfo
                  h3 Ticket Info
                  label Name: {{ s.t_name }}
                  label Phone: {{ s.t_phone }}
                  label Email: {{ s.t_mail }}
                .program-details
                  h3 Program Details
                  label Name: {{ s.p_name }}
                  label Phone: {{ s.p_phone }}
                  label Email:  {{ s.p_mail }}
      .venue-map
          iframe(
            src="https://maps.google.com/maps?width=100%&height=600&hl=en&q=marina%20bay+(Your%20Business%20Name)&ie=UTF8&t=&z=17&iwloc=B&output=embed"
            frameborder="0"
            scrolling="yes"
            marginheight="0"
            marginwidth="0"
          )


</template>

<script>
import venue from 'static/seed/venue'
export default {
  data () {
    return {
      data: venue,
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
section.venue
  background: $white
  .container
    padding-bottom: $space*4
    header
      text-align: left
      h2
        &:after
          content: ''
          @include absolute-w
          top: $space*12
    nav
      padding-bottom: $space*2
      a.btn
        background: none
        box-shadow: none
        color: #888888
        height: 40px
        padding: 0 $space*0.65
      a.btn.btn-primary
        color: #ff007a



    .content
      .detail
        .details
          p
            color: #888888
          .contact
            display: block
            @media (min-width: $breakpoint-tab-1)
              @include flex
              justify-content: flex-start
            .ticketinfo, .program-details
              @include flex
              flex-direction: column
              justify-content: flex-start
              align-items: end
              line-height: $space*2.5
              padding-top: $space
              padding-bottom: $space
            .program-details
              @media (min-width: $breakpoint-tab-1)
                margin-left: $space*2
    .venue-map
      width: 100%
      iframe
        width: 100%
        height: 20rem

main
  display: block
  @media (min-width: $breakpoint-tab-1)
    @include flex
  .location-details, .venue-map
    flex: 1
</style>

