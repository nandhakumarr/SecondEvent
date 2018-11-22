<template lang="pug">
section.speakers
  .container
    header
      span Listen to The
      h2 Event Speakers
    main
      .speakers-list(v-for="(s, i) in data", key="i")
        .speaker-img
          img(:src="s.image")
        .speaker-info
          h3 {{ s.name }}
          p {{ s.designation }}
    img.memphis1(src="/images/home-speaker-memphis1.png")
    img.memphis2(src="/images/home-speaker-memphis2.png")
    img.memphis3(src="/images/home-speaker-memphis3.png")
</template>

<script>
import speaker from 'static/seed/speakers'
export default {
  data () {
    return {
      data: speaker
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
      flex-wrap: wrap
      .speakers-list
        margin: $space
        .speaker-img
          border-radius: 50%
          width: 15rem
          height: 15rem
          position: relative
          margin: auto auto 1.2rem
          overflow: hidden
          img
            width: 100%
            &:hover
              transform: scale(1)
              transition: all 0.4s ease
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

