<template lang="pug">
section.app-footer
  .container
    .newsletter
      .section-title
        span SUBSCRIBE TO NEWSLETTER
        h2 Want something extra?
      .section-form
        input(id="mail"  type="text" placeholder="Your Email")
        button.btn Subscribe
    .footer  
      .social-media
        ul
          li
            img(src="/images/facebook.png")
          li
            img(src="/images/twitter.png")
          li
            img(src="/images/google+.png")
          li
            img(src="/images/linkedin.png")
          li
            img(src="/images/instagram.png")
      .footer-menu
        ul
          li About Event
          li Blogs
          li Contact
          li Tickets
          li Venue
      .copyrights
        p Copyright  &copy  2018 Exhibz. All Rights Reserved.
</template>

<script>
export default {
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes' 
section.app-footer
  background: #1a1831
  position: relative
  .container
    .newsletter
      background-image: url(/images/subscribe-pattern.png)
      background-image: url(/images/subscribe-slice-left.png)
      background-color: #3b1d82
      background-repeat: no-repeat
      background-size: cover
      height: 20rem
      width: 90%
      margin: 0 auto
      padding: $space*2 0
      margin-top: $space
      z-index: 1
      @include absolute
      top: $space*-24
      text-align: center
      .section-title
        padding-top: $space*2
        span
          padding: $space*2
          font-size: $space
          color: $white
          font-weight: 800
        h2
          padding: $space*2 0
          font-weight: 800
          color: $white
      .section-form
        @include flex
        align-items: flex-end
        margin: $space
        color: $white
        input
          width: 100%
          border: none
          margin: 0 auto
          border-bottom: 1px solid #6f55b0
          background: none
          padding: 1rem
          #mail
            color: $white
        .btn
          @media (max-width: $breakpoint-tab-1)
            padding: 0 $space    
    .footer
      padding-top: $space*10
      .social-media, .footer-menu
        text-align: center
        ul
          margin-bottom: $space*2
          li
            display: inline-block
            margin: 1rem
            height: 40px
            list-style: none
            color: #a8a8ad
            font-size: $space*1
            margin: 0.3rem
            img
              width: 45px
              border: 1px solid #525164
              border-radius: 50%
              padding: $space*0.75
      .footer-menu, .copyrights
        text-align: center
        p
          color: #a8a8ad
          font-size: $space*1

</style>

