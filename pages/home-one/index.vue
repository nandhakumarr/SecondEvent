<template lang="pug">
.page
  app-header
  hero
  about
  speakers
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

import Hero from '~/components/sections/hero/Hero'
import About from '~/components/sections/about/About'
import Speakers from '~/components/sections/speakers/Speakers'
import SplitSection from '~/components/sections/split-section/SplitSection'
import Agenda from '~/components/sections/agenda/Agenda'
import Tickets from '~/components/sections/tickets/Tickets'
import Blog from '~/components/sections/blog/Blog'
import Sponsors from '~/components/sections/sponsors/Sponsors'
import Venue from '~/components/sections/venue/Venue'
import AppHeader from '~/components/sections/app-header/AppHeader'
import AppFooter from '~/components/sections/app-footer/AppFooter'
import BookSeat from '~/components/sections/book-seat/BookSeat'

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
    BookSeat
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
<template lang="pug">
.page
  app-header
  hero
  about
  speakers
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

import Hero from '~/components/sections/hero/Hero'
import About from '~/components/sections/about/About'
import Speakers from '~/components/sections/speakers/Speakers'
import SplitSection from '~/components/sections/split-section/SplitSection'
import Agenda from '~/components/sections/agenda/Agenda'
import Tickets from '~/components/sections/tickets/Tickets'
import Blog from '~/components/sections/blog/Blog'
import Sponsors from '~/components/sections/sponsors/Sponsors'
import Venue from '~/components/sections/venue/Venue'
import AppHeader from '~/components/sections/app-header/AppHeader'
import AppFooter from '~/components/sections/app-footer/AppFooter'
import BookSeat from '~/components/sections/book-seat/BookSeat'
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
    BookSeat
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
