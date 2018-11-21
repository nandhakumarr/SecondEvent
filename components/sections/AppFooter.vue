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

section
  .newsletter
    background-image: url(/images/subcribe-pattern.png)
    width: 70rem
    height: 25rem
    // background-color: green
    margin: 0 auto
    padding-top: $space*3
    .section-title
      padding-top: $space*3
      letter-spacing: $space/2
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
      input
        border: none
        border-bottom: 2px solid 
        background: none 
        padding: 1rem     

  
       
    

</style>

