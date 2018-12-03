<template lang="pug">
section.venue-halls
  .container
    header
      span Hurry Up!
      h2 Lecture-Halls
    .lecture-halls
      .halls(v-for="hall in halls")
        img(:src="hall.img")
      
</template>
<script>
export default {
  data(){
    return {
      halls: [
        {img: '/images/venue-1.jpg' },
        {img: '/images/venue-2.jpg' },
        {img: '/images/venue-3.jpg' },
        {img: '/images/venue-4.jpg' }
      ]
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'
section.venue-halls
  .container
    .lecture-halls
      @include flex

</style>
