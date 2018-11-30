<template lang="pug">
section.speakers
  .container
    header
      span Listen to The
      h2 Event Speakers
    main
      component(v-for="(s, i) in data", 
        :is="card"
        :speaker="s"
        @click.native="select(i)"
        :key="i" 
        :class="[{ 'selected': selected === i }]")
      speaker-modal(v-if="selected", :speaker="selected", @close="deselect")

    img.memphis1(src="/images/home-speaker-memphis1.png")
    img.memphis2(src="/images/home-speaker-memphis2.png")
    img.memphis3(src="/images/home-speaker-memphis3.png")
</template>

<script>
import speaker from 'static/seed/speakers'
import SpeakerCircle from '~/components/widgets/SpeakerCircle'
import SpeakerSquare from '~/components/widgets/SpeakerSquare'
import SpeakerModal from '~/components/widgets/SpeakerModal'

export default {
  props: {
    card: {
      type: String,
      default: "speaker-circle"
    }
  },
  data () {
    return {
      data: speaker,
      selected: null
    }
  },
  methods: {
      select(i){
        console.log(i, 'select speaker')
        this.selected = this.data[i]
      },
      deselect() {
        this.selected = null
      }
  },
  components: {
    SpeakerCircle,
    SpeakerSquare,
    SpeakerModal
  }
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.speakers
  background-image: url(/images/speaker-bg.png)
  background-repeat: no-repeat
  background-size: cover
  min-height: 100vh
  padding-bottom: $space*4
  position: relative

  .container
    header
      position: relative
      text-align: center
      margin-bottom: $space*7
      span
        color: $neutral-light
        text-transform: uppercase
    main
      position: relative
      text-align: center
      @include flex
      // padding: $space
      @media (min-width: $breakpoint-mobile)
        justify-content: center
      flex-wrap: wrap

//Extras Images
.memphis1
  @include absolute-nw
  top: 5rem
.memphis2
  @include absolute-se
  top: 10rem
.memphis3
  @include absolute-sw
  bottom: -2rem
  left: 5rem
</style>
