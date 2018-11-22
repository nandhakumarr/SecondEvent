<template lang="pug">
section.app-header(:class="{dark: isScroll}")
  .container(:class="{open: open}")
    a.logo
      img(src="/images/logo.png")
    a.hamburger(@click="toggle()")
      img(src="/images/menu.png")
    nav.navigation(:class="{open: open}")
      .primary
        a(href="#", v-scroll-to="'.hero'") home
        a(href="#", v-scroll-to="'.about'") about
        a(href="#", v-scroll-to="'.speakers'") speakers
        a(href="#", v-scroll-to="'.schedule'") schedule
        a(href="#", v-scroll-to="'.blog'") blog
        a(href="#", v-scroll-to="'.app-footer'") contact
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
      this.isScroll = window.scrollY >= 100
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
    top: $space*-1.2
    @include flex
    background: transparent
    .navigation
      a
        margin: $space
      a.btn.btn-primary
        font-size: 0.9rem
      // ::after
      //   content: '\f107'
        text-decoration: none
      // ::after
      //   content: '\f107'
        
      @media (max-width: 960px) 
        display: none  
    a.hamburger
      margin-right: $space*2
      @media (min-width: 960px) 
        display: none   
        
      


.app-header.dark
  background: rgba(26, 24, 49, 0.95)
  z-index: 99
  transition: background-color 0.35s
  @include fixed-n
  width: 100%
  height: auto
  padding: $space*2.7 0
</style>

