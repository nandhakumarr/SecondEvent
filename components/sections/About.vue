<template lang="pug">
section.about
  .container
    .intro
      .text
        .intro-text(v-for="(a, i) in about.about1", :key="i")
          h3 {{ a.title }}
          p {{ a.description }}
          span {{ a.counterNumber }}
      .video
        .intro-video
          img(src="/images/video-img.jpg")
          //- a(href="https://www.youtube.com/watch?v=Bey4XXJAqS8", @click="open()")
          //-   img(src="/images/video-play.png")
      .text
        .intro-text(v-for="(a, j) in about.about2", :key="j")
          h3 {{ a.title }}
          p {{ a.description }}
          span {{ a.counterNumber }}
</template>

<script>
import data from 'static/seed/about'
export default {

  data () {
    return {
      about: data,
      open: false
    }
  },
  methods: {
    open () {
      this.open = !this.open
    },
    hide () {
      this.open = false
    }
  }

}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.about
  background-color: $bg-white
  background-image: url(/images/lines.png)
  background-repeat: no-repeat
  background-position: center
  padding-top: $space*3
  .container
    // padding: $space*4
    .intro
      @include spread
      flex-wrap: wrap
      margin-right: 15px
      margin-left: 15px
      .text
        .intro-text
          background: $white
          box-shadow: 0px 20px 25px 0px rgba(0, 0, 0, 0.08)
          border-radius: 5px
          padding: $space*2.5 $space*2.8 $space*2.5 $space*2.5
          position: relative
          overflow: hidden
          z-index: 2
          margin-bottom: $space*4.5
          p
            margin-top: $space/2
          p, span
            color: $neutral-light
          span
            @include absolute
            top: auto
            left: auto
            right: -55px
            bottom: -55px
            width: 7.5rem
            height: 7.5rem
            border-radius: 50%
            background: #e7015e
            color: #fff
            display: block
            text-align: left
            font-weight: 700
            padding: $space*1.5 $space*1.8
      .video
        max-width: 33.33%
        flex: 1
        .intro-video
          width: 32rem
          height: 32rem
          border-radius: 50%
          position: relative
          overflow: hidden
          margin: -5rem
          z-index: 1
          img
            max-width: 100%
            height: 100%
          &:before
            background-image: -webkit-linear-gradient(90deg, #e6005d 0%, rgba(115, 0, 47, 0.35) 65%, rgba(0, 0, 0, 0) 100%)
            position: absolute
            left: 0
            top: 0
            content: ''
            width: 100%
            height: 100%
          a
            @include absolute
            top: 50%
</style>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.about
  @media (max-width: $breakpoint-tab-4)
    background-image: none
  .intro
    display: block
    .text
      @media (min-width: $breakpoint-tab-4)
        max-width: 33.33%
        flex: 1
      .intro-text
        @media (max-width: $breakpoint-minitab)
          // padding-bottom: $space*2 !important
          margin-bottom: $space !important
    .video
      .intro-video
        @media (max-width: $breakpoint-mobile)
          border-radius: 0 !important
          margin-left: -2rem !important
        @media (max-width: $breakpoint-minitab)
          border-radius: 0 !important
          margin-left: -2rem !important
        @media (min-width: 600px) and (max-width: 767px)
          border-radius: 0 !important
          margin-left:  4rem !important
        @media (min-width: $breakpoint-tab-portrait) and (max-width: $breakpoint-tab-4)
          border-radius: 0 !important
          margin-left: 5rem !important
          img
            max-width: 100%
            height: 100%
</style>
