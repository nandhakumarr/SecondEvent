<template lang="pug">
.speaker
  .speaker-img
    img(:src="speaker.image")
    .plus-image
      img(src="https://img.icons8.com/ios/48/cccccc/plus.png")
  .speaker-info
    h3 {{ speaker.name }}
    p {{ speaker.designation }}
</template>

<script>
export default {
  props: {
    speaker: {
      type: Object,
      default: {}
    }
  }
}
</script>


<style lang="sass" scoped>
@import 'assets/styles/includes'

.speaker
  margin: $space
  position: relative
  &:hover
    .speaker-info
      color: $event-pink !important
    .speaker-img
      &:before
        position: absolute
        left: 0
        top: 0
        width: 100%
        height: 100%
        content: ''
        background: rgba(59, 29, 130, 0.5)
        transition: all 0.4s ease
        opacity: 1
        z-index: 1
        cursor: pointer
      img
        transform: scale(1.2)
        transition: all 0.6s ease
      .plus-image
        opacity: 1
        position: absolute
        top: 50%
        left: 37%
        z-index: 10
        color: #fff
        font-size: 22px
        width: 50px
        height: 50px
        margin: auto
        // padding: 12px 0
        // border: 1spx solid #ddd
        transform: translateY(-50%)
        cursor: pointer
  .speaker-img
    width: 15rem
    height: 15rem
    position: relative
    margin: auto auto 1.2rem
    overflow: hidden
    img
      width: 100%
    .plus-image
      opacity: 0
      img
        color: $white
  .speaker-info
    @include absolute-se
    background: $white
    bottom: $space*1.2
    left: $space*1.5
    z-index: 1
    p
      color: $neutral-light
    h3
      &:hover
        color: $event-pink
        cursor: pointer
.speaker
  .speaker-img
    @media (max-width: $breakpoint-minitab)
      margin: auto 6rem 1.2rem !important
</style>
