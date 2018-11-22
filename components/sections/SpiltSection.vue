<template lang="pug">
section.spilt-section
  .cta-image
  .cta-content
    .cta
      span Get Experience
      h2 Shift your perspective on digital business
      p How you transform your business as technology, consumer, habits industry dynamic s change? Find out from those leading the charge.
</template>

<script>
export default {

}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.spilt-section
  @include flex
  position: relative
  .cta-image, .cta-content
    flex: 1
  .cta-image
    background-image: url(/images/cta-img.jpg)
    background-repeat: no-repeat
    background-size: cover
    min-height: 30rem
  .cta-content
    position: relative
    min-height: 30rem
    background: $event-lightblue
    &:before
      content: ''
      background-image: url(/images/cta-bg.png)
      backgroun-repeat: no-repeat
      background-size: cover
      width: 100%
      height: 100%
      @include absolute
    &:after
      content: ''
      background-image: linear-gradient(90deg, #321575 0%, #8d0b93 51%, #ff0066 100%, #ff057c 100%)
      @include absolute
      width: 100%
      height: 100%
      opacity: 0.35
    .cta
      max-width: 36rem
      padding: $space*5 $space*6
      z-index: 1
      position: relative
      h2, span, p
        color: $white !important
      h2
        font-size: 2rem
        margin-bottom: $space*2
        margin-top: $space*2
        letter-spacing: 1.2px
      span
        text-transform: uppercase
        font-size: 1rem
        letter-spacing: 1.4px

section.spilt-section
  @media (max-width: $breakpoint-desktop)
    display: block
    .cta-image, .cta-content
      flex: none
      width: 100%
</style>

