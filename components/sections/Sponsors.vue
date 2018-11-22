<template lang="pug">
section.sponsors
  .container
    .sponsor-title
      span WHO HELP US
      h2 Our Sponsers
    .sponsor-logos
      a(href="#")
        img(src="/images/sponsor1.png")
      a(href="#")
        img(src="/images/sponsor2.png")
      a(href="#")
        img(src="/images/sponsor3.png")
      a(href="#")
        img(src="/images/sponsor4.png")
      a(href="#")
        img(src="/images/sponsor5.png")
      a(href="#")
        img(src="/images/sponsor6.png")
      a(href="#")
        img(src="/images/sponsor7.png")
      a(href="#")
        img(src="/images/sponsor8.png")
      a(href="#")
        img(src="/images/sponsor9.png")
    button.btn BECOME A SPONSOR  

</template>

<script>
export default {

}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.sponsors
  background-image: url(/images/sponsor-img.jpg)
  min-height: 100vh
  .container
    text-align: center
    .sponsor-title
      padding-top: $space*4
      h2
        color: $white
        font-weight: 800
        padding: $space
    .sponsor-logos
      a
        img
          padding: $space*2
    .btn
      margin: $space*1
           


</style>

