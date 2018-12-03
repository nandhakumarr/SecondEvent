<template lang="pug">
.page
  page-hero(pageTitle="Speaker 1", pageSubTitle="Exhibit/ Speaker 1")
  key-speakers(card="speaker-square")
  speakers(card="speaker-square")
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
@import 'assets/styles/includes'
</style>
