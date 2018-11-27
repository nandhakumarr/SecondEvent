<template lang="pug">
nav.navigator(:class="{open: open}")
  ul.primary
    li(v-for="item, i in navigation.primary" :key="i" @click="select(i)" :class="[{'selected': selected === i}]")
      a(href="#", v-scroll-to="item.scroll_to") {{ item.label }}
      img(v-if="item.children", src="/images/dropdown.png")
      ul.dropdown-content(v-if="item.children")
        li(v-if="selected" v-for="child, i in item.children", :key="i") 
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
      selected: null
    }
  },
  data(){
    return{
      navigation: navigation
    }
  },
  methods:{
   select(i){
     this.selected = i
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
      // display: none
      position: absolute
      background: #FFF
      z-index: 100000
      a
        color: #333
        

  // ul.primary > li.active
  //   > ul.dropdown-content
  //     display: block
  //     @include reset-space
  //     li
  //       background: #ddd
  //       a
  //         color: black
  //         padding: $space/2 $space/4 
  //         text-decoration: none
  //         display: block

// .navigator
//   ul.primary
//     li
//       &.active
//         ul.dropdown-content
//           li
//             display: block
//             @include reset-space




.navigator
  .primary
    li
      @include spread
      
         

.navigator
  a
    margin: $space
  a.btn.btn-primary
    font-size: 0.9rem
    text-decoration: none
  @media (max-width: 960px)
    display: none
  &.open
    display: block
    @include fixed-sw
    top: 6rem
    left: auto
    rigth: auto
    width: 90%
    ul.primary  
      flex-direction: column  
      li
        width: 100%
        padding: $space/2
        background: green
        a.btn.btn-primary
          width: 90%

          
          





</style>
