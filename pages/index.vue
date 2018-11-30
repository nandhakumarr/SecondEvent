<template lang="pug">
.page
  app-header
  hero
  about
  speakers(card="speaker-circle")
  speakers(card="speaker-square")
  split-section
  agenda
  tickets
  blog
  sponsors
  venue
  book-seat
  app-footer
  .back-to
    a(href="#", v-scroll-to="'.hero'")
      img(src="/images/dropdown.png")
</template>


<script>

import Hero from '~/components/sections/hero/Hero.vue'
import About from '~/components/sections/about/About.vue'
import Speakers from '~/components/sections/speakers/Speakers.vue'
import SpeakersSquare from '~/components/sections/speakers/SpeakersSquare.vue'
import SplitSection from '~/components/sections/split-section/SplitSection.vue'
import Agenda from '~/components/sections/agenda/Agenda.vue'
import Tickets from '~/components/sections/tickets/Tickets.vue'
import Blog from '~/components/sections/blog/Blog.vue'
import Sponsors from '~/components/sections/sponsors/Sponsors.vue'
import Venue from '~/components/sections/venue/Venue.vue'
import AppHeader from '~/components/sections/app-header/AppHeader.vue'
import AppFooter from '~/components/sections/app-footer/AppFooter.vue'
import BookSeat from '~/components/sections/book-seat/BookSeat.vue'
export default {
components: {
    Hero,
    About,
    Speakers,
    SplitSection,
    Agenda,
    Tickets,
    Blog,
    Sponsors,
    Venue,
    AppHeader,
    AppFooter,
    BookSeat,
    SpeakersSquare
  }
}
</script>

<style>

body {
  background: #333

}
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
.back-to {
    background: #e7015e none repeat scroll 0 0;
    border-radius: 50%;
    bottom: 35px;
    color: #979797;
    cursor: pointer;
    height: 44px;
    position: fixed;
    right: 14px;
    text-align: center;
    width: 44px;
    z-index: 9;
    display: block;
    padding: 8px 0;
}


</style>
