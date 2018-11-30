<template lang="pug">
section.book-seat
  .container
    .book
      header.white
        span Hurry Up!
        h2 Book your Seat
      button.btn Buy Ticket
</template>
<script>

export default {
 
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

section.book-seat
  background-image: url(/images/book-seat-img.jpg)
  background-repeat: no-repeat
  background-size: cover
  min-height: 50vh
  position: relative
  .container
      text-align: center
      position: relative
      .book
        padding-bottom: $space*15
        header
          padding: $space*1.2 
      
</style>
