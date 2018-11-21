<template lang="pug">
section.app-footer
  .container
    .book-seat
      span Hurry Up!
      h2 Book your Seat
      button.btn Buy Ticket
    .newsletter    
      .section-title
        span SUBSCRIBE TO NEWSLETTER
        h2 Want something extra?
      .section-form
        input(type="text" placeholder="Your Email")
        button.btn Subscribe
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
      p Copyright © 2018 Exhibz. All Rights Reserved.     
</template>

<script>
export default {

}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.app-footer
  background-image: url(/images/book-seat-img.jpg)
  background-repeat: no-repeat
  background-size: cover
  min-height: 50vh
section.app-footer
  .container
    text-align: center
    .book-seat
      padding: $space*1.2
      span, a
        color: $white  
      h2
        color: $white
        padding: $space*2
      .btn
        padding: 0 $space*2
        line-height: $space*3.2

section.app-footer
  .container
    .newsletter
      background-image: url(/images/subcribe-pattern.png)
      background-color: green
      margin: 0 auto
      padding: $space*2
      margin: $space
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
        input
          width: 100%
          border: none
          border-bottom: 1px solid #6f55b0
          background: none 
          padding: 1rem     
        .btn
          padding: 0 $space*2
          line-height: $space*3.2
section
  .container
    .social-media, .footer-menu
      text-align: center
      ul
        li
          display: inline-block
      img
        width: 25px
    
       
    

</style>

