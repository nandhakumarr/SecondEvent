<template lang="pug">
section.speakers
  .container
    header
      span Listen to The
      h2 Event Speakers
    main
      .speakers-list(v-for="(s, i) in data", :key="i" :class="[{ 'selected': selected === i }]")
        .speaker-img
          img(:src="s.image")
          .plus-image(@click="select(i)")
            img(src="https://img.icons8.com/ios/48/cccccc/plus.png")
        .speaker-info
          h3 {{ s.name }}
          p {{ s.designation }}
      .speaker-modal(v-if="selected")
        .modal-content
          .mspeaker-img
            img(:src="selected.image")
          .mspeaker-info
            h3 {{ selected.name }}
            p {{ selected.designation }}
            img(:src="selected.logo")
            p {{ selected.content }}
            h4 Session by {{ selected.name }}
            .sessions
              .day1
                h4 Day1
                span {{ selected.time }}
                p {{ selected.topic }}
              .day2
                h4 Day2
                span {{ selected.time }}
                p {{ selected.topic }}
          button
            img(src="https://img.icons8.com/metro/48/000000/multiply.png" @click="deselect()")
    img.memphis1(src="/images/home-speaker-memphis1.png")
    img.memphis2(src="/images/home-speaker-memphis2.png")
    img.memphis3(src="/images/home-speaker-memphis3.png")
</template>

<script>
import speaker from 'static/seed/speakers'
export default {
  data () {
    return {
      data: speaker,
      selected: null
    }
  },
  methods: {
      select(i){
        this.selected = this.data[i]
      },
      deselect() {
        this.selected = null
      }
  }
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.speakers
  background-image: url(/images/speaker-bg.png)
  background-repeat: no-repeat
  background-size: cover
  min-height: 100vh
  padding-bottom: $space*4
  position: relative
  
  .container
    header
      position: relative
      text-align: center
      margin-bottom: $space*7
      span
        color: $neutral-light
        text-transform: uppercase
    main
      position: relative
      text-align: center
      @include flex
      // padding: $space
      @media (min-width: $breakpoint-mobile)
        justify-content: center
      flex-wrap: wrap
      .speakers-list
        margin: $space
        &:hover
          .speaker-img
            img
              transform: scale(1.2)
              transition: all 0.5s ease
              filter: grayscale(60%)
            .plus-image
              height: 60%
              opacity: 1     
        .speaker-img
          border-radius: 50%
          width: 15rem
          height: 15rem
          position: relative
          margin: auto auto 1.2rem
          overflow: hidden
          img
            width: 100%
          .plus-image
            @include absolute-s
            opacity: 0
            width: 4rem
            height: 0
            transition: .6s ease
        .speaker-info
          p
            color: $neutral-light
      
//Extras Images
.memphis1
  @include absolute-nw
  top: 5rem
.memphis2
  @include absolute-se
  top: 10rem
.memphis3
  @include absolute-sw
  bottom: -2rem
  left: 5rem
</style>


# Responsive
<style lang="sass" scoped>
@import 'assets/styles/includes'
section.speakers
  .speakers-list
    .speaker-img
      @media (max-width: $breakpoint-minitab)
        margin: auto 6rem 1.2rem !important
</style>

#Modal
<style lang="sass" scoped>
@import 'assets/styles/includes'
section.speakers
  .speakers-list
    position: relative 
  .speaker-modal
    @include fixed
    @include flex
    background: #f4f4f4
    z-index: 100
    max-width: $page-width
    margin: auto
    align-items: flex-start
    height: 35rem
    overflow: auto
    .modal-content
      @include flex
      align-items: flex-start
      text-align: left
      @media (max-width: $breakpoint-tab-3)
        display: block    
      .mspeaker-info
        padding: $space*3
      p
        color: $neutral-light    
      h4, span
        color: $black  
      p, h4, h3, 
        padding-bottom: $space 
      .sessions
        @include flex
        justify-content: flex-start
        .day1, .day2
          h4
            padding: 0rem
        p
          color: #e7015e  
        span
          color: $neutral-light    
          font-weight: bold  
        .day2
          margin-left: $space*3

    button
      border: none     
      padding: $space
      cursor: pointer
      background: none
      img
        width: $space*1.5
    
</style>



