<template lang="pug">
nav.navigator(:class="{open: open}")
  ul.primary
    li(v-for="item, i in navigation.primary", :key="i")
      a(href="#", v-scroll-to="item.scroll_to") {{ item.label }}
      span(v-if="item.children") :::
      ul.dropdown-content(v-if="item.children")
        li(v-for="child, i in item.children", :key="i") 
          nuxt-link(:to="child.url") {{ child.label }}
    li
      a.btn.btn-primary(href="#", v-scroll-to="'.tickets'") Buy Ticket
</template>
<script>
import navigation from 'static/seed/navigation'

export default {
  props: {
    open: {
      type: Boolean,
      required: true
    }
  },
  data(){
    return{
      navigation: navigation
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'


.navigator
  ul.primary
    @media (max-width: 960px)
      display: none
    a.hamburger
      margin-right: $space*2
      @media (min-width: 960px)
        display: none

.navigator
  overflow: visible
  ul.primary
    @include stack-l
    position: relative
    .dropdown-content
      display: none
      position: absolute
      background: #FFF
      z-index: 100000
      a
        color: #333
  ul.primary > li:hover
    > ul.dropdown-content
      display: block
      // li
      //   color: black
      //   padding: 12px 16px
      //   text-decoration: none
      //   display: block

.navigator
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


</style>
