<template lang="pug">
nav.navigator(:class="{open: open}")
  ul.primary
    li(v-for="item, i in navigation.primary", :key="i")
      a(href="#", v-scroll-to="item.scroll_to") {{ item.label }}
       img(v-if="item.children", src="/images/dropdown.png")
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
  overflow: visible
  ul.primary
    @include stack-l
    @include reset-space
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
      @include reset-space
      li
        background: #ddd
        a
          color: black
          padding: $space/2 $space/4 
          text-decoration: none
          display: block
          

.navigator
  a
    margin: $space
  a.btn.btn-primary
    font-size: 0.9rem
    text-decoration: none
  @media (max-width: $breakpoint-tab-5)
    display: none
  

      





</style>
