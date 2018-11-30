<template lang="pug">
.page
  app-header
  page-hero
  venue
  book-seat
  app-footer
  

</template>
<script>
import AppHeader from '~/components/sections/app-header/AppHeader.vue'
import AppFooter from '~/components/sections/app-footer/AppFooter.vue'
import BookSeat from '~/components/sections/book-seat/BookSeat.vue'
import Venue from '~/components/sections/venue/Venue.vue'
import PageHero from '~/components/PageHero/PageHero.vue'
export default {
  components: {
    AppHeader,
    BookSeat,
    AppFooter,
    PageHero,
    Venue
  }
}
</script>
<style lang="sass" scoped>
</style>