<template lang="pug">
section.tickets
  .container
    header.white
      span Pricing Plans
      h2 Get your Ticket
    main
      .pricing-item(v-for="(t, i) in data" key="i")
        img.dot(src="/images/dot.png")
        .pricing-box
          .pricing-header
            h2 {{ t.title }}
            h3 {{ t.price }}
            p Available tickets for this price
          .pricing-progress
            .progress-inner
            p {{ t.progress }}
          .promotional-code
            p.text Enter Promotional code
            a.btn {{ t.cta }}
            p All prices exclude 25% VAT
        img.dot1(src="/images/dot.png")
</template>

<script>
import ticket from 'static/seed/tickets'
export default {
  data () {
    return {
      data: ticket
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.tickets
  background-image: url(/images/pricing-img.jpg)
  background-repeat: no-repeat
  background-size: cover
  min-height: 120vh
  position: relative
  &:before
    @include absolute
    opacity: 0.902
    content: ''
    width: 100%
    height: 100%
    background-image: linear-gradient(144deg, #321575 0%, #8d0b93 51%, #ff0066 100%, #ff057c 100%)
  .container
    main
      @include flex
      flex-wrap: wrap
      position: relative
      .pricing-item
        position: relative
        text-align: center
        .pricing-box
          background: $white
          padding: $space*2.5


.dot
  display: block
  width: 100%
.dot1
  transform: rotate(180deg)
  display: block
  width: 100%
  margin-top: -2px

.pricing-header
  h2, h3
    color: $event-textblue
  p
    color: $neutral-light
    margin-bottom: $space
  h2
    font-size: 1.2rem
    font-weight: 800
    line-height: 1.5rem
    margin-bottom: $space
  h3
    font-size: 3.5rem
    letter-spacing: 1px
    margin-bottom: $space*1.5


.pricing-progress
  width: 100%
  height: 10px
  background: #ebedf4
  margin-bottom: $space*1.5
  .progress-inner
    margin-bottom: $space
    background-image: linear-gradient(144deg, #321575 0%, #8d0b93 51%, #ff0066 100%, #ff057c 100%)
    height: 100%
  p
    color: $event-pink
    font-weight: 800
    margin-bottom: $space*2


.promotional-code
  position: relative
  p.text
    color: $event-pink
    margin-bottom: $space*2
    margin-top: $space*3
  a.btn
    &:before
      @include absolute-w
      content: ''
      width: 25px
      height: 25px
      display: block
      background: #fff
      border-radius: 50%
    &:after
      @include absolute-e
      content: ''
      width: 25px
      height: 25px
      display: block
      background: #fff
      border-radius: 50%
  p
    color: $neutral-light
    margin-top: $space*2
</style>

