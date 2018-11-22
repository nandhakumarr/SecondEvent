<template lang="pug">
section.venue
  .container
    header
      span REACH US
      h2 Get Direction to Event Hall
    .content  
      nav
        a.btn(@click="select(i)", v-for="(v, i) in data", :key="i")  {{ v.tab_name }}
      main
        .detail(v-if="selected === i", v-for="(v,i) in data", :key="i")
          .details(v-for="(s,j) in v.venuetabs" :key="j")
            h3 {{ s.heading }}
            p {{ s.address }}
            .contact
              .ticketinfo
                h3 Ticket Info
                strong Name:
                  p  {{ s.t_name }}
                strong Phone:
                  p  {{ s.t_phone }}
                strong Email:
                  p  {{ s.t_mail }}
              .program-details  
                h3 Program Details
                strong Name:
                  p  {{ s.p_name }}
                strong Phone:
                  p  {{ s.p_phone }}
                strong Email:
                  p  {{ s.p_mail }}
              
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
  .container
    header
      text-align: left
    nav
      padding: $space
      a.btn
        background: none
        color: #888888
        padding: 0 $space 0 0
       
    main
      .detail
        .details
          p
            color: #888888 
          .contact
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
              p
                color: #888888 

</style>

