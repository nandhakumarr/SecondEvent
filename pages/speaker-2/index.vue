<template lang="pug">
.page
  app-header
  page-hero
  key-speakers
  speakers
  book-seat
  app-footer
</template>
<script>
import AppHeader from '~/components/sections/app-header/AppHeader.vue'
import AppFooter from '~/components/sections/app-footer/AppFooter.vue'
import BookSeat from '~/components/sections/book-seat/BookSeat.vue'
import Speakers from '~/components/sections/speakers/Speakers.vue'
import KeySpeakers from '~/components/sections/speakers/KeySpeakers.vue'
import PageHero from '~/components/PageHero/PageHero.vue'
export default {
  components: {
    AppHeader,
    BookSeat,
    AppFooter,
    Speakers,
    KeySpeakers,
    PageHero
  }
}
</script>
<style lang="sass" scoped>
</style>
