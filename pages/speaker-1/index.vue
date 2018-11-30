<template lang="pug">
.page
  .container
    app-header
    .banner-content
      h2 SPEAKERS I
      p Exibit / Speakers I
    book-seat
    app-footer
  

</template>
<script>
import AppHeader from '~/components/sections/app-header/AppHeader.vue'
import AppFooter from '~/components/sections/app-footer/AppFooter.vue'
import BookSeat from '~/components/sections/book-seat/BookSeat.vue'
export default {
  components: {
    AppHeader,
    BookSeat,
    AppFooter
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'
.container
  .banner-content
    background-image: url(/images/banner-bg.jpg)
    background-repeat: no-repeat
    background-size: cover
    height: 400px
    overflow: hidden
    h2, p
      text-align: center
      color: $white
    h2
      margin-top: 10rem

</style>
