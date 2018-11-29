<template lang="pug">
section.app-header(:class="{dark: isScroll, open: open}")
  .container
    a.logo
      img(src="/images/logo.png")
    button
      a.hamburger(@click="toggle()")
        img(src="/images/menu.png")
    NavigationD.desktop(:open="open")
    NavigationM.mobile(:open="open")

</template>

<script>
import Vue from 'vue'
import vueScrollTo from 'vue-scroll-to'
import NavigationD from '~/components/sections/NavigationD.vue'
import NavigationM from '~/components/sections/NavigationM.vue'
Vue.use(vueScrollTo)
export default {
  data () {
    return {
      isScroll: false,
      open: false
    }
  },
  components:{
    NavigationD,
    NavigationM
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
  }
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'


section.app-header
  .container
    @include fixed-n
    @include flex
    background: transparent
    navigationd
      a.btn.btn-primary
        font-size: 0.9rem
      // ::after
      //   content: '\f107'
        text-decoration: none
      // ::after
      //   content: '\f107'

      @media (max-width: $breakpoint-tab-5)
        display: none
      &.open
        display: block

    button
      @media (max-width: $breakpoint-tab-2)
        background: $event-red
        color: $white
        border: 1px solid $event-red
        padding: $space
        border-radius: 2px
        cursor: pointer
        transition: all 0.6s ease
        a.hamburger
          // margin-right: $space*2
          @incliude fixed
          img
            width: 1rem
      @media (min-width: $breakpoint-tab-5)
        display: none






//Sticky
.app-header.dark
  background: rgba(26, 24, 49, 0.95)
  z-index: 1000
  transition: background-color 0.35s
  @include fixed-n
  width: 100%
  height: auto
  padding: $space*3.2 0
  @media (max-width: $breakpoint-tab-5)
    padding: $space*3 0
section.app-header
  .container
    overflow: visible



section.app-header
  .container
    .desktop
      @media (max-width: $breakpoint-tab-5)
        display: none
    .mobile
      @media (min-width: $breakpoint-tab-5)
        display: none
</style>

