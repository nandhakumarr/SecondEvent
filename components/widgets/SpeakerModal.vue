<template lang="pug">
.speaker-modal
  .modal-content
    .mspeaker-img
      img(:src="speaker.image")
    .mspeaker-info
      h3 {{ speaker.name }}
      p {{ speaker.designation }}
      img(:src="speaker.logo")
      p {{ speaker.content }}
      h4 Session by {{ speaker.name }}
      .sessions
        .day1
          h4 Day1
          span {{ speaker.time }}
          p {{ speaker.topic }}
        .day2
          h4 Day2
          span {{ speaker.time }}
          p {{ speaker.topic }}
    button
      img(src="https://img.icons8.com/metro/48/000000/multiply.png" @click="close()")
</template>

<script>
export default {
  props: {
    speaker: {
      type: Object,
      default: {}
    }
  },
  methods: {
    close () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'

.speaker-modal
  @include fixed
  @include flex
  background: #f4f4f4
  z-index: 1000
  max-width: $page-width
  margin: auto
  align-items: flex-start
  height: 35rem
  overflow: auto
  .modal-content
    @include flex
    align-items: flex-start
    text-align: left
    @media (max-width: $breakpoint-tab-3)
      display: block
    .mspeaker-info
      padding: $space*3
    p
      color: $neutral-light
    h4, span
      color: $black
    p, h4, h3,
      padding-bottom: $space
    .sessions
      @include flex
      justify-content: flex-start
      .day1, .day2
        h4
          padding: 0rem
      p
        color: #e7015e
      span
        color: $neutral-light
        font-weight: bold
      .day2
        margin-left: $space*3

  button
    border: none
    padding: $space
    cursor: pointer
    background: none
    img
      width: $space*1.5
</style>

