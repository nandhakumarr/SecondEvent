<template lang="pug">
nav.navigator(:class="{open: open}")
  ul.primary
    li(v-for="item, i in navigation.primary", :key="i" @click="select(i)" :class="[{'selected': isSelected === i}]")
      span
        a(href="#", v-scroll-to="item.scroll_to") {{ item.label }}
        img(v-if="item.children", src="/images/dropdown.png")
      ul.dropdown-content(v-if="isSelected(i)")
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
      required: true,
    }
  },
  data(){
    return{
      selected: null,
      navigation: navigation
    }
  },
  methods:{
   select(i) {
     this.selected = this.selected === i
     ? null
     : i
   },
   isSelected (i) {
     return this.selected === i
   }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'



.navigator
  overflow: visible
  ul.primary
    @include reset-space
    .dropdown-content
      // background: #FFF
      a
        color: white
.navigator
  .primary
    li span
      @include spread
      a
        img
          color: white
.navigator
  a
    margin: $space
  a.btn.btn-primary
    font-size: 0.9rem
    text-decoration: none
  @media (max-width: $breakpoint-tab-5)
    display: none
  &.open
    display: block
    @include fixed-sw
    top: 6rem
    left: 3rem
    rigth: 3rem
    width: 90%
    // margin: 0 auto
    ul.primary
      flex-direction: column
      li
        width: 100%
        padding: $space/2
        background: #222222
        a.btn.btn-primary
          width: 90%








</style>
