<template lang="pug">
.page
  page-hero(pageTitle="Event FAQ's", pageSubTitle="Home/ Faq")
  faq
  book-seat
  app-footer
</template>
<script>
import PageHero from '~/components/PageHero/PageHero.vue'
import Faq from '~/components/sections/faq/Faq.vue'
import AppFooter from '~/components/sections/app-footer/AppFooter.vue'
import BookSeat from '~/components/sections/book-seat/BookSeat.vue'
export default {
  components: {
    PageHero,
    Faq,
    AppFooter,
    BookSeat
  }
}
</script>
<style lang="sass" scoped>

</style>
