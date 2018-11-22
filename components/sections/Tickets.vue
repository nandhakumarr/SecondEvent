<template lang="pug">
section.tickets
  .container
    header.white
      span Pricing Plans
      h2 Get your Ticket
    main
</template>

<script>
export default {

}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.tickets
  background-image: url(/images/pricing-img.jpg)
  background-repeat: no-repeat
  background-size: cover
  min-height: 100vh
  position: relative
  &:before
    @include absolute
    opacity: 0.902
    content: ''
    width: 100%
    height: 100%
    background-image: linear-gradient(144deg, #321575 0%, #8d0b93 51%, #ff0066 100%, #ff057c 100%)
  .container


</style>

