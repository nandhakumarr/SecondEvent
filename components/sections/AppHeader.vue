<template lang="pug">
section.app-header
  .container
    a.logo
      img(src="/images/logo.png")
    nav.navigation
      .primary
        a(href="#", v-scroll-to="'.hero'") HOME
        a(href="#", v-scroll-to="'.about'") ABOUT
        a(href="#", v-scroll-to="'.speakers'") SPEAKERs
        a(href="#", v-scroll-to="'.schedule'") SCHEDULE
        a(href="#", v-scroll-to="'.blog'") BLOG
        a(href="#", v-scroll-to="'.app-footer'") CONTACT
        a.btn.btn-primary(href="#", v-scroll-to="'.tickets'") Buy Ticket

</template>

<script>
import Vue from 'vue'
import vueScrollTo from 'vue-scroll-to'

Vue.use(vueScrollTo)
export default {
  data () {
    return {
      isScroll: false,
      open: false
    }
  },
  created () {
    if (process.client)
      window.addEventListener('scroll', this.handleScroll);
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll);
  },
   methods: {
    handleScroll () {
      this.isScroll = window.scrollY >= 60
    },
    toggle(){
      this.open = !this.open
    },
    show () {
      this.open = true
    },
    hide () {
      this.open = false
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'

section
  .container
    @include fixed-n
    @include flex
    background: transparent
    .navigation
      a
        margin: $space
        text-decoration: none
      ::after
        content: '\f107'
        
      

</style>

