<template lang="pug">
.page
  app-header
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

export default {
  components: {
    AppHeader,
    BookSeat,
    AppFooter,
    Speakers,
    KeySpeakers
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'
</style>
