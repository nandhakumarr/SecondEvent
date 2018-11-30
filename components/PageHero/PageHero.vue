<template lang="pug">
section.page-hero
  .container
    h1 {{ pageTitle }}
    p {{ pageSubTitle }}

</template>
<script>
export default {
  props: {
    pageTitle: {
      type: String,
      default: "Enna page open pannalum andha text varanum"
    },
    pageSubTitle: {
      type: String,
      default: "Inga Subtitle varanum"
    }
  },
  computed: {
    hasTitle () {
      return this.pageTitle.length > 10 ? 'Yay!' : 'Nay :('
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'
section.page-hero
  background-image: url(/images/banner-bg.jpg)
  background-repeat: no-repeat
  background-size: cover
  color: $white
  height: 400px
  overflow: hidden
  @include flex
  .container
    text-align: center

</style>
