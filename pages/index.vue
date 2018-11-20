<template lang="pug">
.page
  hero
  about
  speakers
  spilt-section
  agenda
  tickets
  blog
  sponsors
  venue
  app-footer
</template>


<script>
import Hero from '~/components/sections/Hero.vue'
import About from '~/components/sections/About.vue'
import Speakers from '~/components/sections/Speakers.vue'
import SpiltSection from '~/components/sections/SpiltSection.vue'
import Agenda from '~/components/sections/Agenda.vue'
import Tickets from '~/components/sections/Tickets.vue'
import Blog from '~/components/sections/Blog.vue'
import Sponsors from '~/components/sections/Sponsors.vue'
import Venue from '~/components/sections/Venue.vue'
import AppFooter from '~/components/sections/AppFooter.vue'

export default {
  components: {
    Hero,
    About,
    Speakers,
    SpiltSection,
    Agenda,
    Tickets,
    Blog,
    Sponsors,
    Venue,
    AppFooter
  }
}
</script>

<style>


.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}


</style>
